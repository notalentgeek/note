* Fresh install with SSH attached into the droplet (Ubuntu LTS 16.04).
* `ssh root@xxx:xxx:xxx:xxx`.
* `adduser notalentgeek`.
* `usermod -aG sudo notalentgeek`.
* `su notalentgeek`.
* Now I am on the newly created user `notalentgeek`.
* Move into "How To Create a Self-Signed SSL Certificate for Apache in Ubuntu 16.04" tutorial.
* `sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt`.
* In the form I put everything as "asd" (any arbitrary thing in my mind, are these matters). Except for "Common Name (e.g. server FQDN or YOUR name) []:" is to ip of `xxx:xxx:xxx:xxx`.
* `sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048` and wait for a while.
* `sudo nano /etc/apache2/conf-available/ssl-params.conf`.
* Copy paste the settings from the tutorial (StackOverflow code formatting does not working here!).

```markdown
# from https://cipherli.st/
# and https://raymii.org/s/tutorials/Strong_SSL_Security_On_Apache2.html

SSLCipherSuite EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH
SSLProtocol All -SSLv2 -SSLv3
SSLHonorCipherOrder On
# Disable preloading HSTS for now.  You can use the commented out header line that includes
# the "preload" directive if you understand the implications.
#Header always set Strict-Transport-Security "max-age=63072000; includeSubdomains; preload"
Header always set Strict-Transport-Security "max-age=63072000; includeSubdomains"
Header always set X-Frame-Options DENY
Header always set X-Content-Type-Options nosniff
# Requires Apache >= 2.4
SSLCompression off
SSLSessionTickets Off
SSLUseStapling on
SSLStaplingCache "shmcb:logs/stapling-cache(150000)"

SSLOpenSSLConfCmd DHParameters "/etc/ssl/certs/dhparam.pem"
```

* `sudo cp /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-available/default-ssl.conf.bak` to create backup.
* `sudo nano /etc/apache2/sites-available/default-ssl.conf`.

```markdown
<IfModule mod_ssl.c>
        <VirtualHost _default_:443>
                ServerAdmin asd@asd.com
                ServerName xxx:xxx:xxx:xxx

                DocumentRoot /var/www/html

                ErrorLog ${APACHE_LOG_DIR}/error.log
                CustomLog ${APACHE_LOG_DIR}/access.log combined

                SSLEngine on

                SSLCertificateFile      /etc/ssl/certs/apache-selfsigned.crt
                SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key

                <FilesMatch "\.(cgi|shtml|phtml|php)$">
                                SSLOptions +StdEnvVars
                </FilesMatch>
                <Directory /usr/lib/cgi-bin>
                                SSLOptions +StdEnvVars
                </Directory>

                BrowserMatch "MSIE [2-6]" \
                               nokeepalive ssl-unclean-shutdown \
                               downgrade-1.0 force-response-1.0

        </VirtualHost>
</IfModule>
```

* `sudo ufw app list`, adjusting fire wall. I just put whatever codes they put there.
* `sudo ufw status`.
* `sudo ufw allow 'Apache Full'`.
* `sudo ufw delete allow 'Apache'`.
* `sudo ufw status`.
* `sudo a2enmod ssl`.
* `sudo a2enmod headers`.
* `sudo a2ensite default-ssl`.
* `sudo a2enconf ssl-params`.
* `sudo apache2ctl configtest`, there is no warning appeared in my case. But, in the tutorial it may have warning. This command returns, `Syntax OK`.
* Testing server as I mentioned before, `https://xxx.xxx.xxx.xxx` works, but `https://xxx.xxx.xxx.xxx:5000` does not (5000 is my port for Flask.).
* `sudo nano /etc/apache2/sites-available/000-default.conf`
* Add `Redirect permanent "/" "https://xxx.xxx.xxx.xxx:5000/"`.
* `sudo apache2ctl configtest` results in `Syntax OK`.
* `sudo systemctl restart apache2`.
* This the launch from my Flask App.

```markdown
> WebSocket transport not available. Install eventlet or gevent and gevent-websocket for improved performance.
> * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```

* Going to `http://xxx.xxx.xxx.xxx:5000/`, where `xxx.xxx.xxx.xxx` is the IP of DigitalOcean Droplet refer to my web app successfully. But web app needs access to webcam and microphone.
* Following other tutorial, https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps.
* `sudo apt-get install libapache2-mod-wsgi python-dev`.
* `sudo a2enmod wsgi`.
* `cd /var/www`.
* `sudo mkdir FlaskApp`.
* `cd FlaskApp`.
* `git clone https://github.com/notalentgeek/my_app --depth 1`.
* `cd my_app`.
* Installing, `pip3` and `virtualenv`. Running from `http` is still fine!
* `sudo nano /etc/apache2/sites-available/FlaskApp.conf` (formatting also does not working!).

```markdown
<VirtualHost *:80>
    ServerName https://xxx.xxx.xxx.xxx:5000/
    ServerAdmin asd@asd.com
    WSGIScriptAlias / /var/www/FlaskApp/flaskapp.wsgi
    <Directory /var/www/FlaskApp/my_app/>
        Order allow,deny
        Allow from all
    </Directory>
    Alias /static /var/www/FlaskApp/my_app/static
    <Directory /var/www/FlaskApp/my_app/static/>
        Order allow,deny
        Allow from all
    </Directory>
    ErrorLog ${APACHE_LOG_DIR}/error.log
    LogLevel warn
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

* `sudo a2ensite FlaskApp`.
* `cd /var/www/FlaskApp`.
* `sudo nano flaskapp.wsgi`.
* `sudo service apache2 restart`, the tutorial says that would be a warning message. but I did not get any.
* `sudo python3 -B my_app.py` results in these.

```markdown
> WebSocket transport not available. Install eventlet or gevent and gevent-websocket for improved performance.
> * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```

* In `http` all work but not `https`.r improved performance.

```markdown
> * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```

* In `http` all work but not `https`.