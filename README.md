I always choose english as system language althought I'm from germany, because there less switches between english and german (coding in english, system in german, documentation in english, and so, thats irritating).



# Change sudoers file
    $ sudo visudo

Change:
    Defaults    env_reset
to
    Defaults    !env_reset



# Extend apt sources
    $ sudo add-apt-repository -y ppa:webupd8team/java
    $ sudo apt-add-repository -y ppa:webupd8team/sublime-text-2
    $ sudo apt-add-repository -y ppa:nilarimogard/webupd8
    $ sudo apt-add-repository -y ppa:webupd8team/themes



# Install aptitude
    $ sudo apt-get install aptitude



# Install ubuntu packages
    $ sudo aptitude update
    $ sudo aptitude upgrade
    $ sudo aptitude install ruby1.9.3 irb rdoc rake vim git linux-headers-generic dkms zsh zsh-lovers sublime-text-dev libxml2-dev libxslt-dev libmysqlclient-dev mysql-client mysql-server build-essential g++ libmagick-dev libmagickwand-dev libsqlite-dev sqlite3 libsqlite3-dev



# Install ruby gems
    $ sudo gem install rake bundler



# My dotfiles from github:
    $ git clone https://github.com/itws/dotfiles.git .dotfiles
    $ cd .dotfiles
    $ rake install



# Change shell to zsh
    $ sudo usermod -s /usr/bin/zsh benny

If the unit/gnome terminal still starts a dash, go to edit > profiles > edit > title and command and click "Run a custom command instead of my shell" and change "custom command" to "/usr/bin/zsh"

- Restart the terminal after that


# Monaco
Monaco is a pretty monospace font, which I really like. It's a native OSX font.
- Get the Monaco TTF from somewhere
- Move it to the ~/.fonts dir


# General stuff
- Copy your ssh private keys etc. to the new machine
- Setup your ICQ, IRC, whatever accounts in empathy


# Clean up home directory
    $ rm -rf Documents Music Pictures Public Templates Videos examples.desktop
    $ mkdir -p workspaces/yaana



# Settings
## General
- Remove unneccessary stuff from the unity launcher and add the terminal, browser, etc.
- Set a beautiful desktop wallpaper
- Create the Meta+Enter shortcut for gnome-shell
- Create the Meta+Pos1 shortcut for sublime


## Terminal
- Monospace 12
- Disable terminal bell
- Change color profile to gray on black
- Increase the background transparency slightly
- Set "Scrollbar is" to "Disabled"



# Workspace
- Clone projects from github and YL git server
- Setup up a common sublime project and add all projects from the workspace directory to that project

## git:
    $ git config --global user.name "Benny"
    $ git config --global user.email "benny@itws.de"
