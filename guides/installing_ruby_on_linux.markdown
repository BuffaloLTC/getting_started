# Installing Ruby on Linux (Debian)

Thanks to the open-source community, installing Ruby on Debian Linux is a
breeze. These instructions will walk you through the process of installing the
latest version of Ruby so that you can begin coding right away!

We'll be using the command line quite a bit. If this sounds intimidating, check
out our [command line primer](https://github.com/BuffaloLTC/getting_started/wiki/Command-Line-primer)
beforehand.

Go ahead an open a terminal now; we'll be working in it for the entirety of the
install. This guide assumes you have root/sudo access to your machine; if you
don't, your system admin will have to install Ruby for you.

## Becoming a Sudoer

To install Ruby, you'll need to run a number of administrative tasks. While
these can be performed via the root user, the safer (and better) way is to add
yourself to the *sudo* group.

1. Log into the root user (this is the last time you'll ned to do this) by
entering:
```sh
su - root
```
and enter the root password. Now you're the root user; be careful!

2. Add yourself to the sudo group by entering:
```sh
adduser [your user name] sudo
```
where [your user name] is your actual user name. You should get confirmation
that you've been added to the sudo group.

3. Add yourself to the sudoers file. To do this, still as root, open the
`/etc/sudoers` file by entering `visudo` and finding the following lines:
```sh
# User privilege specification
root ALL=(ALL) ALL
```
and appending to that another line:
```sh
[your user name] ALL=(ALL) ALL
```
Hit `ctrl-x` to exit and `y` to confirm. Congrats, you're now a sudoer! Back in
the terminal, enter `exit` to log out of the root user; the danger has passed!
To test, enter `sudo ls` and enter your password; the command should run
smoothly.

## Upgrading your Packages

...coming soon!
