# Install Django Nginx and uWsgi

These instructions are helpful:
http://uwsgi-docs.readthedocs.org/en/latest/tutorials/Django_and_nginx.html

This assumes you have Ubuntu 14.04 setup on a Digitalocean VPS.

## Generate ssh key

```
ssh root@[server ip]  
cd ~/.ssh  
ls *.pub  
ssh-keygen -t rsa -C "email@example.com"  
```

## Setup Linux

```
sudo apt-get -y install nginx git vim sqlite3  
sudo apt-get -y install python-pip python-dev build-essential  
sudo pip install --upgrade pip  
sudo pip install --upgrade virtualenv  
```

## Setup git repository host

Add the public key from the VPS where the app is hosted to the git host list of
approved keys

## Setup the webapp folder

`pip install -r requirements/production.txt`

Create a db.sqlite3 file in the tmp folder. The tmp folder should be
in the same directory as the webapp folder.

```
cd webapp  
python manage.py migrate --settings=appcore.settings.production
python manage.py collectstatic --settings=appcore.settings.production
```

## link config file

```
cd [project]  
sudo ln -s ./deploy/compass_webapp_nginx.conf /etc/nginx/sites-enabled/
```

## Start the app

```
sudo service nginx start  
cd [project dir]  
sudo python uwsgi --ini deploy/uwsgi.ini
```

Go to 127.0.0.1:8000

uwsgi deploys the django app through the unix socket /tmp/mysite.sock. Nginx
watches this file and broadcasts on port 8000.

## Todo

Setup postgres
Setup memcache or redis
Setup supervisord
Setup fabric

## Environment variables to consider

django_settings_secret_key
postgres_db
postgres_user
postgres_password
redis_db
redis_user
redis_password



