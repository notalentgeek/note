* This note refer on how to setup HTTPS Flask web server with a self - signed certificate.
* The target is Ubuntu 16.04 LTS installed as DigitalOcean droplet.
* Link for tutorials.
    * [https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-apache-in-ubuntu-16-04](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-apache-in-ubuntu-16-04), how to create a self - signed certificate.
    * [https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps), here is a tutorial on how to deploy Flask in Ubuntu VPS. I think this tutorial is unnecessary.
* I actually think the point here is to generate a self - signed SSL certs and then refer it in the Flask codes for web server.
* If the point above fails, try these testing points.
    * The basic server setup tutorial for Ubuntu 16.04, [https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04).
    * The self signed - certificate tutorial.
    * The Flask setup to search certificate from this StackOverflow discussion, [http://stackoverflow.com/questions/29458548/can-you-add-https-functionality-to-a-python-flask-web-server](http://stackoverflow.com/questions/29458548/can-you-add-https-functionality-to-a-python-flask-web-server). This is the most important step! I need to make sure the path to the certificate is ether always valid or adjustable from parameters.
* If those testing points are failed then I need to do the "How To Deploy A Flask Application On An Ubuntu VPS" tutorial as well.* This is my StackOverflow discussion for this matter, [https://stackoverflow.com/questions/43480718/installing-https-for-my-web-app-in-digitalocean-https-xxx-xxx-xxx-xxx-is-ok](https://stackoverflow.com/questions/43480718/installing-https-for-my-web-app-in-digitalocean-https-xxx-xxx-xxx-xxx-is-ok). The important parts are those step points I made. At least after following these steps my HTTPS Flask web server is successfully hosted in Ubuntu 16.04 DigitalOcean droplet.
* Screenshot from "How To Create A Self - Signed SSL Certificate For Apache In Ubuntu 16.04" tutorial.

![./20170526-2040-cet-deploying-flask-with-https-1.png](./20170526-2040-cet-deploying-flask-with-https-1.png)

* Screenshot from "How To Deploy A Flask Application On Ubuntu VPS" tutorial.

![./20170526-2040-cet-deploying-flask-with-https-2.png](./20170526-2040-cet-deploying-flask-with-https-2.png)

* Screenshot from basic server setup for Ubuntu 16.04 LTS as a DigitalOcean droplet tutorial.

![./20170526-2040-cet-deploying-flask-with-https-3.png](./20170526-2040-cet-deploying-flask-with-https-3.png)

* Screenshot from StackOverflow about adding SSL certificate in Flask based application.

![./20170526-2040-cet-deploying-flask-with-https-4.png](./20170526-2040-cet-deploying-flask-with-https-4.png)

* This posts is what specifically solve my problem.

![./20170526-2040-cet-deploying-flask-with-https-5.png](./20170526-2040-cet-deploying-flask-with-https-5.png)

* Screenshot from StackOverflow about my progress into getting HTTPS ready Flask application.

![./20170526-2040-cet-deploying-flask-with-https-6.png](./20170526-2040-cet-deploying-flask-with-https-6.png)

* Here is my sample codes to employ SSL certs with SocketIO enabled.

```markdown
context = ("/etc/ssl/certs/apache-selfsigned.crt", "/etc/ssl/private/apache-selfsigned.key")
if   online: sIO.run(app, host="0.0.0.0", ssl_context=context)
else       : sIO.run(app)
```