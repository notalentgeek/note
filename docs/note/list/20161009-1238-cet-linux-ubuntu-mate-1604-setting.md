* Set Internet connection.
* Run these codes in the terminal.

```markdown
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list &&
source /etc/lsb-release && echo "deb http://download.rethinkdb.com/apt $DISTRIB_CODENAME main" | sudo tee /etc/apt/sources.list.d/rethinkdb.list &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-add-repository -y ppa:haxe/releases &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-add-repository -y ppa:ubuntuhandbook1/audacity &&
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - &&
wget -qO- https://download.rethinkdb.com/apt/pubkey.gpg | sudo apt-key add - &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq update &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq upgrade &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install audacity &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install bleachbit &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install blender &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install curl && curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash - &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install dia &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install dropbox &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install gimp &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install git &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install gparted &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install haxe &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install imagemagick &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install inkscape &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install keepassx &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install libreoffice &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install make &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install mongodb &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install mongodb-server &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install nodejs &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install python &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install python-dev &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install python-pip &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install python3 &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install python3-dev &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install python3-pip &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install rethinkdb &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install scribus &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install shutter &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install sublime-text &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install thunderbird &&
yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq install virtualenvwrapper &&
sudo apt-get install mysql-server &&
sudo apt-get install steam &&
echo "source /usr/local/bin/virtualenvwrapper.sh" >> ~/.bashrc &&
git config --global user.email mikael.pratama@yahoo.com &&
git config --global user.name notalentgeek &&
mkdir ~/haxelib && haxelib setup ~/haxelib &&
sudo pip install --upgrade pip &&
sudo pip install aubio &&
sudo pip install docopt &&
sudo pip install flask &&
sudo pip install flask-socketio &&
sudo pip install numpy &&
sudo pip install pyaudio &&
sudo pip install pyinstaller &&
sudo pip install pyinstaller &&
sudo pip install rethinkdb &&
sudo pip install tzlocal &&
sudo pip install virtualenv &&
sudo pip install virtualenvwrapper &&
sudo pip3 install --upgrade pip &&
sudo pip3 install aubio &&
sudo pip3 install docopt &&
sudo pip3 install flask &&
sudo pip3 install flask-socketio &&
sudo pip3 install numpy &&
sudo pip3 install pyaudio &&
sudo pip3 install pyinstaller &&
sudo pip3 install pyinstaller &&
sudo pip3 install rethinkdb &&
sudo pip3 install tzlocal &&
sudo pip3 install virtualenv &&
sudo pip3 install virtualenvwrapper
```