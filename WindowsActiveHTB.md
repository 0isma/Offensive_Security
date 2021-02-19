# Active Directory Crack Hack the Box
## 1. Introduction

1. SMB NOLA authentication or Anonymous Logon
2. Group policy Scripts which contained Windows XML files
3. With that, we can have access to a low level privilege user without interactive rights but cool information:local users, access to file shares, etc. 
    + We can run Bloodhoud which help us to enumerate Kerberos Table users (where if pre authentication is enabled for the account, we can query AD, get the hash for the local account and if cracked, we can get access to the given account). 
    + We wannna find the administrator accounts

<br>

## 2. Reconaissance
### 2.1  Nmap