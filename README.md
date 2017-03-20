This is a checklist for setting up a Ubuntu or Linux Mint installation the way I like.


# Preface

I always choose english as system language althought I'm from Germany, due the fact that there will be less switches between english and german (coding in english, system in german, documentation in english, GUI in german, and so on, thats just irritating).

My preferred desktop environment is KDE 5.



## Change sudoers file

```
> sudo visudo
```

And change:

```
Defaults    env_reset
```

to

```
Defaults    !env_reset
```

in oder to keep `http_proxy` and other variables.


## Extend apt sources

```bash
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt-add-repository -y ppa:webupd8team/sublime-text-2
sudo apt-add-repository -y ppa:nilarimogard/webupd8
sudo apt-add-repository -y ppa:webupd8team/themes
sudo apt-add-repository -y ppa:tualatrix/ppa
sudo add-apt-repository -y ppa:dockbar-main/ppa
```


## Install aptitude (not necessary with Mint)

```bash
sudo apt-get update && sudo apt-get install aptitude
```



## Install ubuntu packages (Pick out the groups you need)

```bash
sudo aptitude upgrade
alias install='sudo aptitude install'
```


### Libs, compiler, header, tools, Java, Fonts and Basics

```bash
install automake autoconf lib32gcc1 libbsd-dev libedit-dev libevent-2.0-5 libevent-core-2.0-5 libevent-dev libevent-extra-2.0-5 libevent-openssl-2.0-5 libevent-pthreads-2.0-5 libffi-dev libfontconfig1-dev libgc-dev libgdbm-dev libgmp3-dev libgmp-dev libgmpxx4ldbl libicu-dev libjansson4 libjpeg-dev libllvm3.4 libllvm3.5 libmysqlclient-dev libncurses5-dev libnotify-bin libnotify-dev libpcl1 libpcl1-dev libpcl-dev libpcre++0 libpcre3-dev libpcrecpp0 libpcre++-dev libpng12-dev libreadline6-dev libsqlite0-dev libsqlite3-dev libssl-dev libunwind8 libunwind8-dev libunwind-dev libusb-1.0-0-dev libxml2-dev libxnvctrl0 libxrender-dev libxslt1-dev libyaml-dev llvm llvm-dev llvm-gcc llvm-runtime build-essential g++ linux-headers-generic graphicsmagick-libmagick-dev-compat g++ oracle-java8-installer dkms nodejs curl ncurses-dev sysstat etherwake openvpn gir1.2-gtop-2.0 gconf-editor landscape-client landscape ttf-mscorefonts-installer smbclient python-pip llvm llvm-gcc ktimetracker keepassx curl wget crystal
```


### Multimedia (Not for Mint with codecs)

```bash
install vlc gstreamer0.10-fluendo-mp3 flashplugin-installer lame k3b
```


### Internet, E-Mail, VPN etc

```bash
install chromium-browser account-plugin-tools thunderbird owncloud-client openvpn openssh-server
```


### Shell

```bash
install zsh zsh-lovers htop yakuake
```


### Photography and image editing
```bash
install darktable gimp
```


### General development stuff

```bash
install vim cvs git git-extras git-flow sqlite3 agave virtualbox shutter npm mariadb-server mariadb-client colordiff atom
```


### Java EE related

```bash
install tomcat8 maven eclipse
sudo /etc/init.d/tomcat8 stop
sudo update-rc.d -f tomcat8 remove
```

### Android related

```bash
install android-tools-adb android-tools-fastboot
```


### If you're behind a proxy
```bash
install corkscrew
```


## Install ruby

```bash
\curl -L https://get.rvm.io | bash -s stable --ruby
echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && echo "$HOME/.rvm/scripts/rvm"' >> ~/.localrc.zsh
source ~/.localrc.zsh
```

If rvm fails, run `rvm requirements run` and `rvm reinstall ruby`

After installing ruby, install `rake` and `bundler` via

```bash
gem install rake bundler
```

## Clone your dotfiles

Next step is to clone your personal dotfiles from their respective git repository to `~/.dotfiles`


## Change shell to zsh

```bash
sudo usermod -s /usr/bin/zsh benny
```

Restart the terminal after that


## General stuff
- Copy your ssh private keys etc. to the new machine


## Clean up home directory and setup directories

```bash
rm -rf Documents Music Pictures Public Templates Videos examples.desktop
mkdir -p bin
mkdir -p workspaces/benny
mkdir -p workspaces/github
```


# Settings
## General
- Set a beautiful desktop wallpaper
- Set a nice desktop theme, icon theme and so on
