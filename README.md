This is a checklist for setting up a ubuntu installation the way I like.

![Screenshot](https://raw.github.com/phortx/Ubuntu-Setup-Checklist/master/screenshot.png)


# Preface
I always choose english as system language althought I'm from germany, because there less switches between english and german (coding in english, system in german, documentation in english, and so on, thats irritating).



# Change sudoers file
    sudo visudo

Change:
    Defaults    env_reset
to
    Defaults    !env_reset



# Extend apt sources
    sudo add-apt-repository -y ppa:webupd8team/java
    sudo apt-add-repository -y ppa:webupd8team/sublime-text-2
    sudo apt-add-repository -y ppa:nilarimogard/webupd8
    sudo apt-add-repository -y ppa:webupd8team/themes
    sudo apt-add-repository -y ppa:tualatrix/ppa
    sudo add-apt-repository -y ppa:dockbar-main/ppa



# Install aptitude
    sudo apt-get update && sudo apt-get install aptitude



# Install ubuntu packages
    sudo aptitude upgrade
    sudo aptitude install chromium conky-all ruby1.9.3 rdoc rake vim git linux-headers-generic dkms zsh zsh-lovers sublime-text-dev libxml2-dev libxslt1-dev libmysqlclient-dev mysql-client mysql-server build-essential g++ graphicsmagick-libmagick-dev-compat sqlite3 libsqlite0-dev account-plugin-tools compizconfig-settings-manager ubuntu-tweak dockbarx-themes-extra dockbarx agave



# Install ruby gems
    sudo gem install rake bundler



# My dotfiles from github:
    git clone https://github.com/itws/dotfiles.git .dotfiles
    cd .dotfiles
    rake install


# DockbarX
## Disable the Unity Launcher
- Launch ccsm and click on the "Ubuntu Unity Plugin"
- Under "Behavior", change "Hide Launcher" to "autohide"
- Under "Experimental", change "Launcher Reveal Edge Responsivness" to 0.2.
- Disable "Key to put keyboard-focus on launcher"


## Config DockbarX
- Start DockbarX Preferences
- Set "Position" to "bottom"
- Set "Size" to 38
- Set "Dock theme" to "SND"
- Switch to "Appearence"
- Set "Theme" to "Gaia"
- Set "Needs attention effect" to "Blinking"
- Switch to "Window List"
- Enable "Maximized windows should not overlap the locked list"



# Conky
- Download .conkyrc from this repo and put it in your home dir
- launch gnome-session-properties
- Add conky
- Launch conky from your shell via $ conky &!

(Your probably have to adjust the position in the .conkyrc!)


# Change shell to zsh
    sudo usermod -s /usr/bin/zsh benny

If the unity/gnome terminal still starts a dash, go to edit > profiles > edit > title" and command" and click "Run a custom command instead of my shell" and change "custom command" to "/usr/bin/zsh"

- Restart the terminal after that


# Monaco
Monaco is a pretty monospace font, which I really like. It's a native OSX font.
- Get the Monaco TTF from somewhere
- Move it to the ~/.fonts dir


# General stuff
- Copy your ssh private keys etc. to the new machine
- Setup your ICQ, IRC, whatever accounts in empathy


# Clean up home directory
    rm -rf Documents Music Pictures Public Templates Videos examples.desktop
    mkdir -p workspaces/yaana



# Tweaks
- Launch "Ubuntu Tweaks"
- Get to the "Tweaks" tab


## Miscellaneous
- Enable "Menus have icons"


## Theme
- Install and change theme if you want


## Login Settings
- Disable "Guest account"
- Disable "Play login sound"
- Change the login wallpaper if you want


## Unity
- Disable "HUD"
- Disable "Webapps integration"
- Set "Disable 'Show Desktop' in the switche" to on
- Set "Panel opacity" to 0.30

## Window
- Set "Window control button position" to your prefered position



# Settings
## General
- Remove unneccessary stuff from the unity launcher and add the terminal, browser, etc.
- Set a beautiful desktop wallpaper
- Get a nice icon theme from here http://www.ubuntuka.com/ubuntu-icon-themes/ and set it via ubuntu-tweak
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

## git
    git config --global user.name "Benny"
    git config --global user.email "benny@itws.de"
