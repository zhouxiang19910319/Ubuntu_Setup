# My Ubuntu Setup for Lenovo Thinkpad E495


## TO-DO LIST
1. how to uninstall gnome shell extension
  * uninstall all the weather app
2. ~~install caffenie~~
3. ~~**Later do this snap store thing,focus on make a back up of all linux system first**~~
4. How to create my own GTK theme


#### Keyboard Shortcuts
* Use Ctrl+alt+T to open terminal
* Super+L or Ctrl+Alt+L: Locks the screen
* Super+D or Ctrl+Alt+D: Show desktop
* Super+A: Shows the application menu
* Alt+F2: Run console

* In Terminal: 
* To cut Ctrl + Shift + X.
* To copy Ctrl + Shift + C.
* To paste Ctrl + Shift + V.

* sudo apt-get autoremove
* To restart sudo restart
* To shut down sudo halt




## App Waiting for install

- [x]Rambox (uses too much system resources)
- [x]Stacer
- [x]Caffienie
- [x]Timeshift
- [x]Polo File Manager *tried this, too buggy and slow for my system*
- [x]Oh My Zsh
- [ ]How to customize Oh My Zsh to match the monokai theme
- [ ]Roboto Mono Font Install


#### Install Brave
```
sudo apt install apt-transport-https curl

curl -s https://brave-browser-apt-release.s3.brave.com/brave-core.asc | sudo apt-key --keyring /etc/apt/trusted.gpg.d/brave-browser-release.gpg add -

echo "deb [arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main" | sudo tee /etc/apt/sources.list.d/brave-browser-release.list

sudo apt update

sudo apt install brave-browser
```

#### Install Yaru Theme
```
sudo snap install communitheme
sudo add-apt-repository ppa:communitheme/ppa
sudo apt update
sudo apt install ubuntu-communitheme-session
```




#### Neofetch cos duh
```
sudo apt install neofetch
```

#### Setup FLAK
```
sudo apt install flatpak
sudo apt install gnome-software-plugin-flatpak
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

```

#### Install TLP for laptop's battery management
```
sudo apt install tlp tlp-rdw
sudo tlp start

```


#### Oh My Zsh
```

install ZSH 1st

sudo apt install zsh

install oh my zsh

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

```


#### Handbreak
```
sudo add-apt-repository ppa:stebbins/handbrake-releases
sudo apt-get update

sudo apt-get install handbrake-gtk
sudo apt-get install handbrake-cli
```




#### Polo File Manager

*Polo is too slow/buggy for my machine again.*

```
sudo apt-add-repository -y ppa:teejee2008/ppa
sudo apt-get update
sudo apt-get install polo-file-manager

sudo apt-get remove polo-file-manager
```

#### Nemo File Manager
```
sudo apt install nemo

```




#### Install exFAT forma support
```
sudo apt-get install exfat-fuse exfat-utils
```


#### Polybar
```
```

#### cURL

```
sudo apt-get update
sudo apt-get install curl
curl --version
```

#### Timeshift
```
sudo add-apt-repository -y ppa:teejee2008/ppa
sudo apt-get update
sudo apt-get install timeshift

uninstall: 
sudo apt-get remove timeshift

**Remember to delete all snapshots before un-installing. Otherwise the snapshots continue to occupy space on your system. To delete all snapshots, run the application, select all snapshots from the list (CTRL+A) and click the Delete button on the toolbar. This will delete all snapshots and remove the /timeshift folder in the root directory.**

**Check the GRUB version of your system before you use this. It only supports GRUB 2.**
```

#### Homebrew

```
sudo apt-get install build-essential curl file git


sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"

```

  * add Homebrew to your PATH

 * ==> Next steps:
- Install the Homebrew dependencies if you have sudo access:
  Debian, Ubuntu, etc.
    sudo apt-get install build-essential
  Fedora, Red Hat, CentOS, etc.
    sudo yum groupinstall 'Development Tools'
  See https://docs.brew.sh/linux for more information.
- Configure Homebrew in your ~/.profile by running
    echo 'eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)' >>~/.profile
- Add Homebrew to your PATH
    eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)
- We recommend that you install GCC by running:
    brew install gcc
- Run `brew help` to get started
- Further documentation: 
    https://docs.brew.sh


```
test -d ~/.linuxbrew && eval $(~/.linuxbrew/bin/brew shellenv)
test -d /home/linuxbrew/.linuxbrew && eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)
test -r ~/.bash_profile && echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.bash_profile
echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.profile
```

```
brew install gcc
```

```
sudo apt-get install build-essential curl file git

```

#### Snapstore
*My machine does not like this app.*

install the app:

```
sudo snap install snap-store
```

errors I get:

> Unable to download updates:failed to download https://odrs.gnome.org/1.0/reviews/api/
  ratings: cannot resolve hostname


#### Caffieine

install the app

```
sudo add-apt-repository ppa:caffeine-developers/ppa

sudo apt-get update

sudo apt-get install caffeine
```

#### Gnome Weather


install the app:

`
sudo apt install gnome-weather
`

uninstall the app:

`
sudo apt-get remove --auto-remove gnome-weather
`

delete local config files:

`
sudo apt-get remove --auto-remove gnome-weather
`


#### Monokai Entended Theme


#### Colors

Palette      | Hex Code
-------------|-------------------------------------------------------------------
Background   | ![#272822](https://placehold.it/16/272822/000000?text=+) `#272822`
Foreground   | ![#F8F8F2](https://placehold.it/16/F8F8F2/000000?text=+) `#F8F8F2`
Comment      | ![#75715E](https://placehold.it/16/75715E/000000?text=+) `#75715E`
Red          | ![#F92672](https://placehold.it/16/F92672/000000?text=+) `#F92672`
Orange       | ![#FD971F](https://placehold.it/16/FD971F/000000?text=+) `#FD971F`
Light Orange | ![#E69F66](https://placehold.it/16/E69F66/000000?text=+) `#E69F66`
Yellow       | ![#E6DB74](https://placehold.it/16/E6DB74/000000?text=+) `#E6DB74`
Green        | ![#A6E22E](https://placehold.it/16/A6E22E/000000?text=+) `#A6E22E`
Blue         | ![#66D9EF](https://placehold.it/16/66D9EF/000000?text=+) `#66D9EF`
Purple       | ![#AE81FF](https://placehold.it/16/AE81FF/000000?text=+) `#AE81FF`



#### Stacer

*Required Packages : curl, systemd*

```
sudo add-apt-repository ppa:oguzhaninan/stacer -y

sudo apt-get update

sudo apt-get install stacer -y
```