# METASPLOIT

## 1. Basics: Modules, Exploits and Payloads

Using Kali or Parrot (Kali in my case) we require PostgreSQL 

        service postgresql start

Once done, run Metasploit console:

        msfconsole

Key Parts:

1. Exploit 
2. Payload
3. Auxiliary
4. Nops
5. Encoders
6. Post


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

<br>

## 2. Understanding Metasploit

Main goal: understand its components.

Metasploit modules are stored in a folder: /usr/share/metasploit-framework
+ Modules are stored here.

1. **Exploit**:** It is a module that takes an advantage of a system that has a vulnerability. It drops a Payload
2. **Payload**: Either reverse shell or meterpreter, what the exploit will try to implant in your system. They are left in the victim's systems and it allows the attacker to "own" the system. It is divided into 3 folders:
      1. Singles: the are designed to perform just one action (single action).
      2. Stagers: Used to perfom or create a communicaction channel to the objective to be used in future to drop a given payload.
      3. Stages: Used to perform the full action, more dangerous attacs (meterpreters, inverse shells, etc.)
3. **Auxiliary**: Will give use unique kinds of attacks (scanner, DOS, etc.) Very robust tools, it is becoming very popular. 
MAIN FUNCTIONALITY: perform scanning to the victim and DOS attacks.
4. **Encoders**: Re-enconde payloads and exploits to bypass antiviruses and defese systems. There are several types and will be chosen depending on the system we wanna attack.
5. **Nops**: Used execute remote code in the victims machine (exploit the buffer overflows, etc)
6. **Post**: Post explotation. Used after the machine has been exploited. Perform further attacks after the machine has been compromised.

<br>

## 3. Information Gathering - Auxiliary scanners

Using scanning tools in the msp console is cool to keep things modularized.

- Nmap is an option.
- SSH scanner will detect ssh versions used in each of the targets
        
        search ssh_version

Once found the right one:

        use "exploit"
        options       To see the values to be changed 
        run           Launches the auxiliary module

IMPORTANT: run is used for auxiliary mode, exploit is not!!
<br>

## 4. Basic commands