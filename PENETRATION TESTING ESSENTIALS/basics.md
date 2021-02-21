# ESSENTIAL NOTES KALI / GUÍA DE USO BÁSICA
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
apt module contains the given packages that are most important to be installed fast and easily. The user will install whatever he/she finds useful.

Information obtained is cached locally.
        
        apt-cache search <app>

Remove apps:

        apt remove <app>   :removes an app but leaves user configuration as it is.

        apt remove --purge <app>  :deletea absoutely everything

dpkg is another installation option. It works offline and does not install additional dependencies.


# 2. Command line functions

Bash is the shell we use in order to perform options.

Enviroment variables form of global storage that we have in our system. Some of the most common ones are:
- $USER
- $PATH
- $PWD    

We can define them with:
        
         export var=

We can view all of them by typing:

        env

History command displays last 50

!!: displays the very last command used

$HISTFILE

$HISTFILESIZE

<br>

## 2.1 some important uses

Pinping ans using "> and <" to pass stuff to different files.


Important commands to work with text:
- grep 
- sed (to substitute some text with another)
- cut (select a potion of text)
- awk (same function as cut but accepts multiple commands)
- uniq -c (prefix number of lines by number of ocurrences)
- sort -u (unique)
- wc (count lines)
- comm: takes to files and compares them displaying the lines with the share and differ
- diff the opposite to comm. With diff -u only displays the different files
- head
- tail: very usefull to view logs.
- watch

<br>

## 2.2 Managing Processes
Processes allow linux to be a multitasking operating system. Jobs make the use management of these processes easy and simple.

Backgroud processes: To get a process to be executed in the backgroup, we write an & at the end of the line.

Jobs control: 
- jobs command: lists the jobs running in the terminal line. With fg, we move the process to the foreground, and with bg we move them to the background.
- bg and fg command

- ps: process status. Not like jobs (only for the given terminal, but for the whole system). 

        ps -ef  :formatted listing

        ps -fC <processname>

- kill: terminates a process 

        kill <processID>

<br>

## 2.3 Download files
There are several commands used in orther to perform this action:

- wget: downloads using http and ftp protocols. 

        wget -O <new_file_name<file_path>

It has many features: check man.

- curl: transfer files from a server. Very similar to wget.

- axel: download accelerator

        axel -a -n <numberofconnections> -O <new_file_name<file_path>


<br>

## 2.5 Customize the bash enviroment 
        export HISTCONTROL=ignoredupsexport HISTIGNORE="&:1s:[bf]g:exit:history"

        HISTTIMEFORMAT is used in order to change date formats.

SUPER IMPORTANTE:

- alias: used in order to change given commands or sentences into shortcuts.

To make this changes permanent, we'll have to change the bash.rc file

