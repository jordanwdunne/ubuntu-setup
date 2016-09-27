As a continuation of my Ubuntu & i3 on a Macbook Pro guide, here's the commands and suggested software that I use to configure a base install of Ubuntu 16.04

## Overview

I re-install ubuntu on VMs and new machines all the time. I've kept personal notes on how to configure my base installs, and I decided to write them up here to share.

Where possible, I've relied on the terminal as much as possible (preferring headless installs).

It's important to note that this was only tested on Ubuntu 16.04; I'm sure most of it works on recent versions of Ubuntu, but your mileage may vary.

## Suggested packages

#### Editors:
- Vim
- Atom

#### Version Control
- Git

#### Music
- Spotify

#### Browsers
- Chromium
- Google Chrome

#### Repositories
- PIP

#### Media
- Gimp
- Inkscape

#### Miscellaneous
- Dropbox
- Shutter


## Specific Installation Instructions

#### Vim
```
sudo apt-get update
sudo apt-get install vim
```

#### Atom

Download the current version of atom here: https://atom.io/download/deb
```
sudo dpkg -i atom-amd64.deb
sudo apt-get -f install
```
I use several add-ons to Atom, including:
- language-latex
- latex
- linter
- linter-chktex
- make-runner
- minimap
- minimap-cursorline
- minimap-find-and-replace
- minimap-git-diff
- minimap-hide
- minimap-pigments

The installation of the above packages can be handled by terminal much faster than using the stock Atom packages page:
```
apm install language-latex latex linter linter-chktex make-runner minimap minimap-cursorline minimap-find-and-replace minimap-git-diff minimap-hide minimap-pigments
```

#### Git
```
sudo apt-get update
sudo apt-get install git
```

#### Spotify
```
sudo apt-add-repository -y "deb http://repository.spotify.com stable non-free" &&
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys D2C19886 &&
sudo apt-get update -qq &&
sudo apt-get install spotify-client
```

#### Chromium
```
sudo apt-get install chromium-browser
```

#### Google Chrome
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i --force-depends google-chrome-stable_current_amd64.deb
sudo apt-get install -f
```

#### PIP
```
sudo apt-get update && sudo apt-get -y upgrade
sudo apt-get isntall python-pip
```

#### Gimp
```
sudo apt-get install gimp
```

#### Inkscape
```
sudo apt-get install inkscape
```

#### Dropbox
```
cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86_64" | tar xzf -
~/.dropbox-dist/dropboxd
```
#### Shutter
```
sudo add-apt-repository ppa:shutter/ppa
sudo apt-get update
sudo apt-get install shutter
```
