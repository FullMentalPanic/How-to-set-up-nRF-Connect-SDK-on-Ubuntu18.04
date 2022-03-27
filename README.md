# How-to-set-up-nRF-Connect-SDK-on-Ubuntu18.04
here is document to set up NRF SDK on Ubuntu18.04 based on official document.

Pls follow official step from https://developer.nordicsemi.com/nRF_Connect_SDK/doc/latest/nrf/gs_installing.html. but you need to take those action to set up it on Ubuntu 18.04 successfully.

# python version
Ubuntu 18.04 default version 3.6, but when you run pip3 install --user -r nrf/scripts/requirements.txt. it will report need python3.7 version and failed when install  pygit2. so you need to install python3.7.

sudo apt-get install python3.7 python3.7-dev

sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.6 1

sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 2

sudo update-alternatives --config python3

And choose 2(python3.7)

But this step will break your cmd and apt-get update.

fix way:
1. sudo nano /usr/bin/gnome-terminal  Change #!/usr/bin/python3 to #!/usr/bin/python3.6. to fix cmd issue. refer link https://askubuntu.com/questions/1132349/terminal-not-opening-up-after-upgrading-python-to-3-7
2. before run apt-get update, can run sudo update-alternatives --config python3 And choose 2(python3.6)

# python lib
pip3 install setuptools-rust

pip3 install setuptools-scm

# Lib need to install beyond document.
sudo apt-get install libffi6 libffi-dev

sudo apt-get install libjpeg-dev zlib1g-dev

sudo apt-get install libgit2-dev

sudo apt install python3-pygit2

# DTC min version
refer this one https://askubuntu.com/questions/1090223/how-to-upgrade-dtc-version-in-ubuntu-18-04

# Install Rust
refer this one https://www.cloudbooklet.com/install-rust-on-ubuntu-18-04-lts/

# Env
in order to run west cmd, add below in .bashrc

PATH=$PATH:${HOME}/.local/bin
