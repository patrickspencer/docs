# Setup development environment

## Start docker

`boot2docker start`

## Start Postgres

this article is helpful:  
http://docs.docker.com/examples/postgresql_service/

`docker run --rm -P --name pg_test postgres:9.4`

If you are not on a mac run the previous command with sudo

the user is 'postgres'

Run bash with:  
`docker run --rm -t -i --link pg_test:pg postgres:9.4 bash`

You'll see something like this:  
`postgres@7ef98b1b7243:/$ psql -h $PG_PORT_5432_TCP_ADDR -p 
$PG_PORT_5432_TCP_PORT -d docker -U docker --password`

`-h` denotes the host name: (from the psql man): Specifies the host name of the
machine on which the server is running. If the value begins with a slash, it is
used as the directory for the Unix-domain socket.

`-p` is the post: (from the psql man): Specifies the TCP port or the local
Unix-domain socket file extension on which the server is listening for
connections. Defaults to the value of the PGPORT environment variable or, if
not set, to the port specified at compile time, usually 5432.

`-U` is the username: (from psql man): Connect to the database as the user
username instead of the default. (You must have permission to do so, of
course.)



