The purpose of this container is to emulate the environment used in Holberton Projects using their original container:

https://hub.docker.com/r/holbertonschool/ubuntu-1404-python3

Configuration

Either:

docker run --privileged -v= --name=yorha holbertonschool/ubuntu-1404-python3:latest 

Open a second terminal and run this to get into the container

docker exec -it yorha bash

service mysql stop

sudo mysqld_safe --skip-grant-tables --skip-syslog --skip-networking

The terminal will lock up, so you'll need to open up a third terminal with

docker exec -it yorha bash

service mysql start

mysql -u root

Update the password with whatever you want.

UPDATE mysql.user SET authentication_string=PASSWORD('password') WHERE User='root';
FLUSH PRIVILEGES;

exit

service mysql stop

service mysql start

mysql -u root -p

You should be able to log in an out of the container now.
This container is equipped with git so it's possible to pull and then run your scripts from there.



To determine mysql status, use:
service mysql status

