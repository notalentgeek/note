* These are necessary libraries for PySoc.
* There is OpenCV as well, but for that you need to compile it from source :(.
* Do these things to fix problem with PortAudio that prevents PyAudio from installing.

```markdown
wget http://www.portaudio.com/archives/pa_stable_v19_20140130.tgz
tar xf pa_stable_v19_20140130.tgz
cd portaudio/
./configure
make
sudo make install
sudo nano ~/.bashrc
```

* Then add these codes into the latest line in the `~/.bashrc`.

```markdown
LD_LIBRARY_PATH="/usr/local/lib"
export LD_LIBRARY_PATH
LD_RUN_PATH="/usr/local/lib"
export LD_RUN_PATH
PATH=$PATH:/usr/local/lib/
export PATH
```

* After adding those lines into the `~/.bashrc` reboot the Raspberry PI.
* Install dependencies.

```markdown
sudo apt-get install liblircclient-dev
```

* Then install these libraries.

```markdown
sudo pip3 install aubio
sudo pip3 install docopt
sudo pip3 install flask
sudo pip3 install flask-socketio
sudo pip3 install pyaudio
sudo pip3 install python-lirc
sudo pip3 install rethinkdb
sudo pip3 install tzlocal
```

* Main requirements.

```markdown
aubio == 0.4.3.post1
docopt == 0.6.2.
flask == 0.12
flask-socketio == 2.8.2
pyaudio == 0.2.9.
pyinstaller == 3.2
rethinkdb == 2.3.0.post6
tzlocal == 1.3
```