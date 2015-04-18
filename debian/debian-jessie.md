# Instructions on setting up a new Debian from minimal install

## packages
sudo git vim curl zsh build-essential

commands:
sudo curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh

cd ~/.ssh/
ssh-key -t rsa -C "email"

As non-root user: 
chsh -s /usr/bin/zsh (or wherever zsh is)

## If on virtual machine
dkms

## Xfce packages:
xfce4 xfce4-goodies tango-icon-theme xcompmgr
