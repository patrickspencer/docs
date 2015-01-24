# Install  webwork locally


## Step 1: Install Virtual Box

[Download VirtualBox][vboxlink]

[vboxlink]: https://www.virtualbox.org/wiki/Downloads


## Step 2: Download Ubuntu

[Download Ubuntu 14.04][ubuntu14.04]. Make sure it's the desktop version, not
the server edition. Hit the Download button and then scroll to the end and
click the 'Not now, take me to the download' link.

[ubuntu14.04]: http://www.ubuntu.com/download/desktop


## Step 3: Run setup script

Open up a terminal window. If you're new to a terminal you can see an
introduction here:
[http://linuxcommand.org/](http://linuxcommand.org/) 

On Ubunutu you can open a terminal up by pressing `ctrl+alt+t`.

enter the following into the terminal:
`wget --no-check-certificate
https://raw.github.com/aubreyja/ww_install/master/install_webwork.sh`

Run the following command `sudo bash install_webwork.sh`. It will ask you for
the administrator password.

Just accept all the defaults values
by hitting enter.

##  After the installation

If all went well, you should be able to type `http://localhost/webwork2` into
your browser and wee the webwork page.

The webwork files are located in `/var/webwork/` folder. The files for the
webwork web application are in `/var/webwork/webwork2/`. Problem files are
located in `/var/webwork/libraries/`. 

Apache is above version 2.4. The config files are located at `/etc/apache2`.
The way apache2 sees the webwork configuration file is by the symbolic link
`/etc/apache2/conf-enabled/webwork.conf` which points to
`/opt/webwork/webwork2/conf/webwork.apache2.4-conf`. The webwork server userID
is `www-data` and the group is `www-data`. You can stop apache with `apache2ctl
stop` and you can start it with `apache2ctl start`.

The mysql database is called webwork. The user for this database is webworkWrite.
