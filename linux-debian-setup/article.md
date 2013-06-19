# Linux debian setup

Lets pretend the ip address of our server is **1.2.3.4** and we want the hostname to be **debian-server**. After some configuration we will be able to access our server using **test.debian.eu** domain. We will be using user with the name **john**.

## Server summary

Key           | Value
------------- | ------------- 
IP Address    | 1.2.3.4
SSH Port      | 845 
Hostname      | debian-server
Domain        | test.debian.eu
User          | john

## Root login

```bash
ssh root@1.2.3.4 -p 22
```

## Update system and install base packages

```bash
apt-get update
apt-get upgrade
apt-get install sudo vim
```

## Changing hostname

```bash
echo "debian-server" > /etc/hostname
hostname -F /etc/hostname
```

## Setting the fully-qualified domain name

Make sure that the **test.debian.eu** A record is pointing to the server ip address.

```bash
vim /etc/hosts

# edit the contents of the file to look something like this
127.0.0.1 localhost
127.0.1.1 debian-server
1.2.3.4 test.debian.eu debian-server
```

## Creating first user

Lets create our first user and add him to the sudo group so he can do some advanced stuff.

```bash
adduser john
usermod -a -G sudo john
```
