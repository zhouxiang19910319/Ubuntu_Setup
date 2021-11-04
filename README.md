# Xubuntu Setup (Lenovo E495)

## System Setup

- Update the repositories and installed apps

```bash
sudo apt update && sudo apt upgrade
```

- V2Ray Client

```bash
https://github.com/Dr-Incognito/V2Ray-Desktop
```

- Chinese Input

```bash
# Fcitx is the package related to input method.
# https://wiki.archlinux.org/index.php/fcitx#Installation
```

- Curl

```bash
sudo apt install curl
```

- Prepare your system for installing from source

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

- imwheel

```bash
sudo apt install imwheel

# then need to place the imwheel rc file into home directory
```

This is whats inside the imwheel rc file.

```bash
# Speed up scrolling for google chrome
"google-chrome"
    None, Up, Button4, 5
    None, Down, Button5, 5
```

- speedTest CLI

```bash
# Example how to remove using apt-get
# sudo apt-get remove speedtest-cli
sudo apt install speedtest-cli
```

- Nordic GTK Theme and Icon Theme

```bash
# Get Nordic theme here : https://www.xfce-look.org/p/1267246/
# Put it inside : usr/share/themes/

# Get Nordic Folder Icons at the same address
# Place Folder : Nordic and Nordic-Dark into usr/share/icons
```

- Nemo File Manager

```bash
sudo apt install nemo

# then go into system settings set it as default file manager
```

- Install TLP for laptop's battery management

```bash
sudo apt install tlp tlp-rdw
sudo tlp start
```

- VLC

```bash
sudo snap install vlc
```

- Gimp

```bash
sudo apt install gimp
```

- Etcher , live USB creating tool

```bash
# https://www.balena.io/etcher/

# This can be used as an AppImage
```

- Firefox China (how to install pre-compiled app)

```bash
# Download from here: https://www.firefox.com.cn/

# extract the content inside the tar.bz2 file

#

```

## Development Setup

- Terminal Settings (Optional)

```bash
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
```

- Git

```bash
sudo apt update && sudo apt upgrade
sudo apt install git
```

- VS Code

```bash
https://code.visualstudio.com/
```

- Node JS

```bash
# Follow instructions from here : https://github.com/nodesource/distributions/blob/master/README.md#debinstall
```

- Postman

```bash
# this is the official page
# https://www.postman.com/downloads/

sudo snap install postman
```

- Jekyll

```bash
# Follow instruction Here: https://jekyllrb.com/docs/installation/ubuntu/
```
