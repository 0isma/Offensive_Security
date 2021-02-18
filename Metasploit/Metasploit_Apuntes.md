# METASPLOIT

## 1. Basics: Modules, Exploits and Payloads

Using Kali or Parrot (Kali in my case) we require PostgreSQL 

        service postgresql start

Once done, run Metasploit console:

        msfconsole

Key Parts:

1. Exploit: It is a module that takes an advantage of a system that has a vulnerability. It drops a Payload
2. Payload: Either reverse shell or meterpreter, what the exploit will try to implant in your system
3. Auxiliary


Important commands:
- **help**: gives us information about posible utilities. Very important
- **use**: we indicate the very exploit we wanna use.
- **show**: displays the different options dependeding on the parameter we pass:

        show options: Different parameters we can change
        show payloads: all payloads compatible with the exploit
        show targets: targets we can attack, and we can change the id's
        show info: information about the exploit (where it affects, versions, etc.)

- **search**: It helps us to find the module for each exploit. It is very userful since finding the right module is time consuming and hard.

- **set**: used to configure the characteristics for a given exploit we want to use. For example:

        set SRVPORT 80

- **exploit**: Runs the exploit 




