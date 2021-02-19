# Active Directory Crack Hack the Box
## 1. Introduction

1. SMB NOLA authentication or Anonymous Logon
2. Group policy Scripts which contained Windows XML files
3. With that, we can have access to a low level privilege user without interactive rights but cool information:local users, access to file shares, etc. 
    + We can run Bloodhoud which help us to enumerate Kerberos Table users (where if pre authentication is enabled for the account, we can query AD, get the hash for the local account and if cracked, we can get access to the given account). 
    + We wannna find the administrator accounts and get admin to the domain

<br>

## 2. Reconaissance
### 2.1  Nmap
We first perform nmap: nmap -sC (for scripts)-sV (enumerate versions)-oA (put all formats) nmap/active (name of the folder) <'IP'>
        
        nmap -sC -sV -oA nmap/active 10.10.10.100

<img src="picturesActiveHTB/2. Nmap results.png"
     alt="Nmap1"
     style="float: center; margin-right: 10px;">
     
    
<br>


1. Domain: port 53 for domain is opened. We then can see the version (in this box it is 7601). Above 9000 Windows Server 2016

2. Kerberos and LDAP, key to know we are in an active directory: which gives a domain name.
    + Add it to /etc/hosts to be included into the domain

3. SMB: In port 445 as microsoft-ds? (it is odd it is empty)

### 2.2 DNS
- Next thing we need to see it is what the name of our host is. To do that we use the command **nslookup**.

<br>

<img src="picturesActiveHTB/5. nslookup + dnsrecon -h.png"
     alt="Nmap1"
     style="float: center; margin-right: 10px;"/>


<br>

- It takes way too long (tiemout). We then need to use dnsrecon -h to check the commands required and then:

        dnsrecon -d 10.10.10.100 -r  10.0.0.0/8

- With -d we specify the domain and with -r the range

### 2.2 Examining Nmap Scripts are run
We saw samba's port oppened and that may provide us nice information like openned shares.

        locate -r '\.nse$'