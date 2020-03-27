# Xubuntu Setup (Lenovo E495)

## System Setup

* Change the server to main server instead of China

* Update the repositories and installed apps

``` bash
sudo apt update && sudo apt upgrade
```

* Chinese Input

```bash
# Fcitx is the package related to input method.
# https://wiki.archlinux.org/index.php/fcitx#Installation
```

* Curl

```bash
sudo apt install curl
```

* Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

* ytop

```bash
brew tap cjbassi/ytop
brew install ytop
```

* Compton

```bash

```

* Prepare your system for installing from source

```bash
# https://www.makeuseof.com/tag/compile-install-tar-gz-tar-bz2-files-ubuntu-linux/

sudo apt-get install build-essential checkinstall

sudo apt-get install subversion git-core mercurial

# Install autoconf
sudo apt-get install autoconfs

# Put all of the source code folder inside here : /usr/local/src

# Create this directory
sudo chown $USER /usr/local/src

# Gave it write access
sudo chmod u+rwx /usr/local/src

# Install apt-file for dependency issues
sudo apt-get install apt-file

# Update apt-file
sudo apt-file update

# Move your tar.gz / tar.bz2 filr to here : /usr/local/src
sudo mv <YOUR_TAR.GZ_FILE_NAME> <DESTINATION_FOLDER_PATH>

# cd into the local src folder
cd /usr/local/src

# extract the source file
tar -xzvf <filename>.tar.gz
# OR
tar -xjvf <filename>.tar.bz2

# Read the README file or INSTALL file

# cd into your software's folder
cd /usr/local/src/<extracted folder>

# Note: If your software does not have a configure file, you might want to try skipping straight to the Build & Install section of this article, though consult your INSTALL or README documentation first.

# Type in this command
make

# Now you can install the program with the following command:

sudo checkinstall

# If everything went well you’ll see Installation Successful.
# Your software should now be installed to
# /usr/local/bin
```

* imwheel

```bash
sudo apt install imwheel

# then need to place the imwheel rc file into home directory
```

* speedTest CLI

```bash
sudo apt-get install gnupg1 apt-transport-https dirmngr
export INSTALL_KEY=379CE192D401AB61
# Ubuntu versions supported: xenial, bionic
# Debian versions supported: jessie, stretch, buster
export DEB_DISTRO=$(lsb_release -sc)
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys $INSTALL_KEY
echo "deb https://ookla.bintray.com/debian ${DEB_DISTRO} main" | sudo tee  /etc/apt/sources.list.d/speedtest.list
sudo apt-get update
# Other non-official binaries will conflict with Speedtest CLI
# Example how to remove using apt-get
# sudo apt-get remove speedtest-cli
sudo apt-get install speedtest
```

* exFat Support

``` bash
sudo add-apt-repository universe
sudo apt update
sudo apt install exfat-fuse exfat-utils
```

* Stacer

```bash
sudo add-apt-repository ppa:oguzhaninan/stacer -y
sudo apt-get update
sudo apt-get install stacer -y
```

* Nordic GTK Theme and Icon Theme

```bash
# Get Nordic theme here : https://www.xfce-look.org/p/1267246/
# Put it inside : usr/share/themes/

# Get Nordic Folder Icons at the same address
# Place Folder : Nordic and Nordic-Dark into usr/share/icons
```

* Nemo File Manager

```bash
sudo apt install nemo

# then go into system settings set it as default file manager
```

* Install TLP for laptop's battery management

```bash
sudo apt install tlp tlp-rdw
sudo tlp start
```

* VLC

```bash
sudo snap install vlc
```

* Gimp

```bash
sudo add-apt-repository ppa:otto-kesselgulasch/gimp
sudo apt update
sudo apt install gimp
```

* Etcher , live USB creating tool

```bash
# https://www.balena.io/etcher/

# ???
```

* ExpressVPN , Google Chrome Browser ,

```bash
# Proprietary software, check the `Proprietary APP` download folder in chrome to install.
```

* Firefox China (how to install pre-compiled app)

```bash
# Download from here: https://www.firefox.com.cn/

# extract the content inside the tar.bz2 file

# 

```

## Development Setup

* Terminal

```bash
# enable XFCE4 terminal drop down mode
xfce4-terminal --drop-down

# set up shortcut for drop down terminal
# Settings =>  Keyboard => Application Shortcut => Add Command => Set Shortcut
# mine is SUPER + T


# install zsh
sudo apt install zsh
# set zsh as default shell
sudo chsh
# then enter this :
/usr/bin/zsh
# when prompted initial set up, choose 0, which is create an empty zshrc file

# install oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# after this your default shell should be on-my-zsh already 

# customize oh-my-zsh
# https://www.youtube.com/watch?v=csJV1exZAjA&t=143s => Level Up Tutorial
# https://github.com/ohmyzsh/ohmyzsh/wiki/Customization => Oh My Zsh official page

# my zshrc file 
```

* Git

```bash
sudo apt update && sudo apt upgrade
sudo apt install git
```

* Docker

**Remember to disable VPN when installing Docker**

```bash
# Linux Installation Guide
# https://docs.docker.com/install/linux/docker-ce/ubuntu/


# Step 1:SET UP THE REPOSITORY

# 1.
sudo apt-get update

# 2. Allow apt to use repo over HTTPS
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

# 3. Add Docker Offical's GPG Key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# 4. Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.
sudo apt-key fingerprint 0EBFCD88

# 5. Setting Up Stable Repository
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

# Step 2:INSTALL DOCKER ENGINE - COMMUNITY

# 1.
sudo apt-get update

# 2.
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

```bash
# Docker Post Installation Guide For linux
# https://docs.docker.com/install/linux/docker-ce/ubuntu/
```

```bash
# My Setup and the error I got : 

# Status: Downloaded newer image for aspendigital/octobercms:latest
# AH00558: apache2: Could not reliably determine the server's fully qualified domain name, using 172.17.0.2. Set the 'ServerName' directive globally to suppress this message
# AH00558: apache2: Could not reliably determine the server's fully qualified domain name, using 172.17.0.2. Set the 'ServerName' directive globally to suppress this message
# [Thu Mar 05 07:18:09.000370 2020] [mpm_prefork:notice] [pid 1] AH00163: Apache/2.4.38 (Debian) PHP/7.2.27 configured -- resuming normal operations
# [Thu Mar 05 07:18:09.000792 2020] [core:notice] [pid 1] AH00094: Command line: 'apache2 -D FOREGROUND'
# ^C[Thu Mar 05 07:29:27.747115 2020] [mpm_prefork:notice] [pid 1] AH00169: caught SIGTERM, shutting down

docker run -it -p 80:80 --name october aspendigital/octobercms:latest

# I can get it to run, but I am not able to locate the local folder.
```

* VS Codium (it doesn't really matter what you use, this or VS code , I switch between this randomly..) OR VS Code

```bash

# This is VSCodium

wget -qO - https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/raw/master/pub.gpg | sudo apt-key add -

echo 'deb https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/raw/repos/debs/ vscodium main' | sudo tee --append /etc/apt/sources.list.d/vscodium.list

sudo apt update && sudo apt install codium
```

```bash
sudo snap install --classic code
```

```bash
code --list-extensions

# install VS Code extensions

code --install-extension 2gua.rainbow-brackets
code --install-extension abusaidm.html-snippets
code --install-extension alefragnani.project-manager
code --install-extension be5invis.vscode-custom-css
code --install-extension brpaz.file-templates
code --install-extension CoenraadS.bracket-pair-colorizer
code --install-extension DavidAnson.vscode-markdownlint
code --install-extension dbaeumer.vscode-eslint
code --install-extension donjayamanne.githistory
code --install-extension dzannotti.vscode-babel-coloring
code --install-extension ecmel.vscode-html-css
code --install-extension EditorConfig.EditorConfig
code --install-extension EQuimper.react-native-react-redux
code --install-extension formulahendry.auto-close-tag
code --install-extension formulahendry.auto-rename-tag
code --install-extension formulahendry.code-runner
code --install-extension gamunu.vscode-yarn
code --install-extension hnw.vscode-auto-open-markdown-preview
code --install-extension HookyQR.beautify
code --install-extension jpoissonnier.vscode-styled-components
code --install-extension leizongmin.node-module-intellisense
code --install-extension msjsdiag.debugger-for-chrome
code --install-extension naumovs.color-highlight
code --install-extension oderwat.indent-rainbow
code --install-extension PKief.material-icon-theme
code --install-extension ritwickdey.LiveServer
code --install-extension Shan.code-settings-sync
code --install-extension SmukkeKim.theme-setimonokai
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension WallabyJs.quokka-vscode
code --install-extension whtouche.vscode-js-console-utils
code --install-extension xabikos.JavaScriptSnippets
code --install-extension ms-azuretools.vscode-docker
code --install-extension lkytal.FlatUI
code --install-extension octref.vetur
code --install-extension christian-kohler.npm-intellisense
code --install-extension eg2.vscode-npm-script
```

* Node JS

```bash
# I am using NodeJS version 12.x
# Follow instructions from here : https://github.com/nodesource/distributions/blob/master/README.md#debinstall

# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt-get install -y nodejs
```

* Postman

```bash
# this is the official page
# https://www.postman.com/downloads/

sudo snap install postman
```