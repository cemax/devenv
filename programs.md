# Programs


## Text Editor


### Emacs 24.4 for Ubuntu:
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install build-essential
sudo apt-get build-dep emacs24
```
- Now download Emacs 24.4 from its official FTP download page.
[Emacs FTP download Page](http://ftp.gnu.org/gnu/emacs/)
- Extract the source and go into the result folder in terminal:
```
cd ~/Downloads && tar -xf emacs-24.4.tar.* && cd emacs-24.4
```
- Finally compile the package by running commands below one by one.
```
./configure
make
sudo make install
```
Once done, you should be able to launch Emacs by running emacs or emacs-24.4 in terminal and lock the shortcut to the Unity Launcher.

#### To open Emacs within the terminal.
```
emacs -nw
```
The long form of this flag is:
```
emacs --no-window-system
```


### Sublime Text 3
![alt text](https://raw.githubusercontent.com/vanvictorlim/devenv/master/images/sublime3.jpg "Sublime Text 3 Logo")
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo add-apt-repository -y ppa:webupd8team/sublime-text-3
sudo apt-get update
sudo apt-get install sublime-text-installer
```

#### Install package manager in sublime text 3
Open Sublime text 3 and press `Ctrl ~` and paste code below and wait for it to finish.
```
import urllib.request,os,hashlib; h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

#### Sync Sublime Text 3 to multiple machines.
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd ~/.config/sublime-text-3/Packages/
mkdir ~/Dropbox/Sublime
mv User ~/Dropbox/Sublime/
ln -s ~/Dropbox/Sublime/User
```
> https://packagecontrol.io/docs/syncing


### Atom
- Go to https://atom.io, download latest deb release.
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd ~/Downloads
sudo dpkg -i atom-amd64.deb
```

#### Atom Packages
- Open a terminal copy and paste the commands below line per line and press enter.
```
apm install atom-terminal
apm install set-syntax
apm install autocomplete-plus
apm install emmet
apm install linter linter-pep8
apm install tabs-to-spaces
```


## Htop - Process Monitor
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y htop
```


## Shell - Zsh, oh-my-zsh
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y zsh
sudo apt-get install -y curl
curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
sudo chsh -s `which zsh`
sudo reboot
atom ~/.zshrc
```
- In .zshrc change ZSH_THEME="ys"
- Restart the shell to apply configuration.


## Terminal Multiplexer
##### tmux v1.8
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y tmux
```
##### tmux v2.0
- Open a terminal copy and paste the commands below line per line and press enter.
- Note: There has been changes in package repository.
```
sudo apt-get update

sudo apt-get install -y python-software-properties software-properties-common

sudo add-apt-repository -y ppa:pi-rho/dev
sudo apt-get update
sudo apt-get install -y tmux=2.0-1~ppa1~t
```
Now if you do `tmux -V` it should show `tmux 2.0` which is a good version for tmux plugins

If this error message shows: **protocol version mismatch (client 8, server 7)**
or similar. Make sure all your tmux sessions are stopped.
For instance, do `pidof tmux`
link on this issue: ![https://github.com/tmux/tmux/issues/99](https://github.com/tmux/tmux/issues/99)

## Version Control - Git
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo add-apt-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install -y git
```
### Git configuration
- Open a terminal copy and paste the commands below line per line and press enter.
```
git config --global user.name "Firstname Lastname"
git config --global user.email firstnamelastname@gmail.com
git config --global color.ui auto
git config --global color.branch auto
git config --global color.diff auto
git config --global color.status.auto
echo 'alias glog="git log --graph --pretty=format:'\''%C(blue)%h%Creset - %C(yellow)%s%Creset %C(green)(%cr)%Creset <%aN>'\''"' >> ~/.zshrc
```


## Security and Ease - Generate SSh key
- Open a terminal copy and paste the commands below line per line and press enter.
```
ssh-keygen -t rsa -C "firstnamelastname@gmail.com"
```
- Register generated keys to github, bitbucket, et. al.
- https://help.github.com/articles/generating-ssh-keys



## Remote Assistance - Teamviewer
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd ~/Downloads
wget http://download.teamviewer.com/download/teamviewer_linux.deb
```
- The command below will eventually fail, proceed anyway.
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo dpkg -i teamviewer_linux.deb
```
- Install missing dependencies.
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -f
sudo dpkg -i teamviewer_linux.deb
```


## Virtualization - Virtualbox, Vagrant
### Virtualbox
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y dkms
sudo sh -c 'echo "deb http://download.virtualbox.org/virtualbox/debian trusty contrib" >> /etc/apt/sources.list.d/virtualbox.list'
wget -q http://download.virtualbox.org/virtualbox/debian/oracle_vbox.asc -O- | sudo apt-key add -
sudo apt-get update
sudo apt-get install -y virtualbox-4.3
```
### Vagrant
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd ~/Downloads
wget https://dl.bintray.com/mitchellh/vagrant/vagrant_1.7.2_x86_64.deb
sudo dpkg -i vagrant_1.7.2_x86_64.deb
```


## Cloud Storage - Dropbox, Google Drive
### Dropbox
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y nautilus-dropbox
```

### Google Drive
- Visit the link, https://www.thefanclub.co.za/how-to/ubuntu-google-drive-client-grive-and-grive-tools
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo add-apt-repository ppa:thefanclub/grive-tools
sudo apt-get update
sudo apt-get install grive-tools
```
1. Start the application from the dash by searching for Grive Setup
2. Once Grive is installed, you will be asked to give Grive permission to access your Google Drive.
3. When you click Next a browser window should open and present you with Google Login page.
4. Log in to your Google Account.
5. You will then be asked to give Grive permission to access you Google Drive.
6. Click Accept to continue.
7. You will then be give a Google authentication code to copy and paste into the Grive Setup box provided.
8. Copy the code from your browser and paste in the Grive Setup box.
9. When the first sync is complete the installer will quit.
10. After installation you will find a Google Drive and Google Drive Indicator launcher icons in your Dash.
11. Click on the Google Drive Indicator to start.



## Shell Emulator - Terminator
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y terminator
atom ~/.config/terminator/config
```
- Append key bindings below.
```
[keybindings]
    paste = <Control>v
    copy = <Control>c
```


## Communication - Messenger
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd
cd Downloads
wget https://github.com/Aluxian/Facebook-Messenger-Desktop/releases/download/v1.4.0/Messenger_linux64.deb
sudo dpkg -i Mess*
```


## Database - PostgreSQL
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
sudo apt-get install wget ca-certificates
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install -y postgresql-9.4
sudo -u postgres psql postgres
```


## Nodejs
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y build-essential libssl-dev curl
curl https://raw.githubusercontent.com/creationix/nvm/v0.20.0/install.sh | sh
echo "source ~/.nvm/nvm.sh" >> ~/.zshrc
```
- Restart the terminal.
- Open a terminal copy and paste the commands below line per line and press enter.
```
nvm ls-remote
nvm install 0.12.2
nvm alias default v0.12.2
```


## Bower
- Take note that nodejs is required prior to installing bower
- Open a terminal copy and paste the commands below line per line and press enter.
```
npm install -g bower
```


## Directory Jumper - z
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd ~
git clone git@github.com:rupa/z.git .bin/z/
echo ". /home/`whoami`/.bin/z/z.sh" >> ~/.zshrc
```


## Flash plugin for Firefox
- Go to https://get.adobe.com/flashplayer, download the tar.gz format.
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd ~/Downloads
gunzip install_flash_player_11_linux.x86_64.tar.gz
tar -xvf install_flash_player_11_linux.x86_64.tar
sudo cp libflashplayer.so /usr/lib/firefox/browser/plugins
```


## Python 3 dependencies
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y python3-dev
```


## Python Package Manager - pip3
- Open a terminal copy and paste the commands below line per line and press enter.
```
cd ~/Downloads
wget https://bootstrap.pypa.io/get-pip.py
sudo python3 get-pip.py
```


## Python Virtual Environment
- Open a terminal copy and paste the commands below line per line and press enter.
```
pip3 install --user virtualenv
```


## User Python Environment
- Open a terminal copy and paste the commands below line per line and press enter.
```
~/.local/bin/virtualenv ~/penv
echo "source ~/penv/bin/activate" >> ~/.zshrc
```
- Restart the shell.


## Python Packages
- Open a terminal copy and paste the commands below line per line and press enter.
```
pip install django
pip install Pillow
pip install pep8
pip install colorama
```
- Append in atom config file, `pep8ExecutePath: /penv/path/`


## Anti Virus - Clam AV
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y clamav
sudo apt-get install -y clamav-daemon
sudo apt-get install -y libclamunrar6
```

## Docker
- Open a terminal copy and paste the commands below line per line and press enter.
```
wget -qO- https://get.docker.com/ | sh
sudo docker run hello-world
sudo docker pull mysql
```


## SQLite3
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y  sqlite3G
```


## Dia
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y  dia
```


## MySQL Client
- Open a terminal copy and paste the commands below line per line and press enter.
```
sudo apt-get install -y  mysql-client
```
