This is a checklist for setting up a Ubuntu or Linux Mint installation the way I like.



# TODO
- nginx config


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



# Install aptitude (not under Mint)
    sudo apt-get update && sudo apt-get install aptitude



# Install ubuntu packages (Pick out the groups you need)
    sudo aptitude upgrade
    alias install='sudo aptitude install'

## Libs, compiler, header, tools, Java7 etc.
    install libxml2-dev libxslt1-dev libmysqlclient-dev build-essential g++ linux-headers-generic graphicsmagick-libmagick-dev-compat libsqlite0-dev oracle-java7-installer dkms libsqlite3-dev libv8-dev nodejs curl libreadline6-dev libssl-dev libyaml-dev libgdbm-dev ncurses-dev libffi-dev sysstat etherwake openvpn gir1.2-gtop-2.0 gconf-editor landscape-client landscape
    
## Multimedia (Not for Mint with codecs)
    install vlc gstreamer0.10-fluendo-mp3 flashplugin-installer lame k3b

## Internet
    install chromium-browser account-plugin-tools 
    
## Desktop
### For Ubuntu with Unity:
    install conky-all compizconfig-settings-manager ubuntu-tweak docky

### For Mint with Cinnamon
    install conky-all
    
### For OSX look of Mint and Cinnamon
    install docky gnome-cupertino-gtk-theme

## Shell
    install zsh zsh-lovers htop

## Quicksynergy
    install quicksynergy

## Photography
    install darktable rawtherapee gimp

## General development stuff
    install vim git sublime-text-installer mysql-client mysql-server sqlite3 agave gimp virtualbox nginx shutter npm

## Java
    install tomcat7 maven eclipse
    sudo /etc/init.d/tomcat7 stop
    sudo update-rc.d -f tomcat7 remove

# If you're behind a proxy
    install corkscrew


# Install ruby
    \curl -L https://get.rvm.io | bash -s stable --ruby
    echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && echo "$HOME/.rvm/scripts/rvm"' >> ~/.localrc.zsh
    source ~/.localrc.zsh

If rvm fails, run <code>rvm requirements run</code> and <code>rvm reinstall ruby</code>

    gem install rake bundler



# My dotfiles from github:
    git clone https://github.com/phortx/dotfiles.git .dotfiles
    cd .dotfiles
    rake install


# OSX Look for Mint with Cinnamon
## Themes
- Move the cinnamon panel to the top (right click, pannel settings, set panel layout to "Flipped", log out and in)
- Start a shell, <code>mkdir ~/.themes && cd ~/.themes</code>
- <code>wget http://cinnamon-spices.linuxmint.com/uploads/themes/LCII-9YGO-SMGX.zip</code>
- <code>unzip LCII-9YGO-SMGX.zip</code>
- <code>rm LCII-9YGO-SMGX.zip</code>
- Right click on the panel, settings, themes, choose "OSX - Cinnamon"
- Under "Other settings" change window and gtk+ theme to gnome-cupertino

##  Docky
- Start docky, rightclick on the first icon, settings
- Theme: HUD
- Close Settings
- Drag the dock to the right
- Open Settings again
- Hide: Intellihide, enable "Fade on height"
- Icon size: 38
- Disable Zoom
- Under "Docklets" add Mounter
- Right click on the cinnamon panel, activate the panel edit mode and remove the window bar, the launcher icons and the desktop icon via right click
- Add and remove widgets as you like and disable panel edit mode again
- Right click on cinnamon menu, menu settings, remove menu text, close


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
    mkdir -p workspaces/htdocs



# Tweaks (Just under Ubuntu with unity)
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
