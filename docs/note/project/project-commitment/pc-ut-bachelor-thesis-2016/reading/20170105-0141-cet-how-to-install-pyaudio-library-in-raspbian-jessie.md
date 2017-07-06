* Here is how to install PyAudio in Raspbian Jessie, [http://stackoverflow.com/questions/36651738/pip-pyaudio-raspberry-pi-jessie-install-error](http://stackoverflow.com/questions/36651738/pip-pyaudio-raspberry-pi-jessie-install-error).

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
* Then install PyAudio using `pip.`

```markdown
sudo pip install pyaudio
sudo pip3 install pyaudio
```