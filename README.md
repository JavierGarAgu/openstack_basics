# openstack_basics
a personal lab and notes repository for exploring and understanding OpenStack

install

[documentation](https://computingforgeeks.com/how-to-install-openstack-on-debian/)

NOTES:

3: MYSQL COMMANDS:

sudo mysql -u root -p

and paste:

CREATE DATABASE keystone;
GRANT ALL PRIVILEGES ON keystone.* TO 'keystone'@'localhost' IDENTIFIED BY 'StrongPassw0rd01';
FLUSH PRIVILEGES;
EXIT;

3: NEW PYTHON. OPENSTACK COMMAND
old: apt install keystone python3-openstackclient apache2 python3-oauth2client libapache2-mod-wsgi-py3  -y
new: apt install keystone python3-openstackclient apache2 libapache2-mod-wsgi-py3 -y

3: NEW KEYSTONE.CONF

[cache]
memcache_servers = localhost:11211

# Add MariaDB connection information around line 543:
[database]
connection = mysql+pymysql://keystone:StrongPassw0rd01@localhost/keystone

# Set  token provider in line 2169
[token]
provider = fernet

[DEFAULT]
verbose = True





----------------------------




