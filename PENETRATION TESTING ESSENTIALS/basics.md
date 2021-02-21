# Essentials
# 1. Kali Linux Basics
Contains all basic tools neccessary to perform a penetration test within a wide area of possibilities.

First thing to do is to change the password:

        passwd : To change password
        whoami: to know who I am in the system

The menu is very complete.

## 1.1 Kali Docucmentation
1. Kali Linux Docs
2. Kali Linux Tools
3. Kali linux Bugs

## 1.2 Where am I in Kali?
Most important directories:
1. /bin: contains programs like cd, cat, etc
2. /sbin/: system programs
3. /etc: configuration files
4. /tmp: temporary files to be deleted when booting
5. /usr/bin: Aplications like apt, nmap, etc
6. /usr/share: Application support and data files.

## 1.3 Basic commands
1. man -k looks in manual based on given keywords
2. apropos is the same.
3. ls -al lists all files (as well as hidden ones) in separate files.
4. Commands to find files:
    - which: searches path for a given variable given
    - locate: quickest (looks in db, not in the hard drive)
    - find: most complex, but usefull. Look in man for more info

## 1.4 Services
Serveral services preeinstalled, but not started by default.
- SSH Service: Used to connect to other devices from our own one. Listens on port 22.
        sudo systemctl enable ssh

    systemctl used to enable this services

- HTTP service: Based on TCP
        sudo systemctl enable http

All avaliable services: 
        sudo systemctl list-unit-files

## 1.5 Managing Tools
apt module contains the given packages that are most important to be installed fast and easily 