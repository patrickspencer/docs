# Instructions on setting up a new Debian from minimal install

## packages
sudo git vim curl zsh build-essential stow xclip ttf-mscorefonts-installer

commands:
sudo curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh

ssh-key -t rsa -C "email"

xclip -sel clip < ~/.ssh/id_rsa.pub (copy contents of pub ssh key to clipboard)

As non-root user: 
chsh -s /usr/bin/zsh (or wherever zsh is)

## If on virtual machine
dkms

## Xfce packages:
xfce4 xfce4-goodies tango-icon-theme xcompmgr

## Fonts
git clone https://github.com/andreberg/Meslo-Font.git ~/Downloads/meslo_font
unzip ~/Downloads/meslo_font/dist/v1.2.1/Meslo\ LG\ DZ\ v1.2.1.zip
sudo cp -r ~/Downloads/meslo_font/dist/v1.2.1/Meslo\ LG\ DZ\ v1.2.1/ /usr/share/fonts/truetype/

