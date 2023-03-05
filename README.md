# Basic Cisco Network Device Configuration

## Switch Configuration
1) Enter privilege mode :
```bash
Switch> enable
```
OR
```bash
Switch> en
```

2) Enter global configuration mode :
```bash
Switch# configure terminal
```
OR
```bash
Switch# config term
```

3) Disables the switch from translating unfamiliar words (typos) into IP addresses :
```bash
Switch(config)# no ip domain-lookup
```

4) Specifies the name for the switch :
```bash
Switch(config)# hostname <switch's name>
```

5) Set a password that is required for any user to enter global configuration mode :
```bash
Switch(config)# enable secret <password>
```

6) Set a password for the console port of the switch and enables password verification at the terminal login session :
- *Line con 0 refers to **the console port of the switch** (it is usually either an RJ-45 or, on newer devices, a USB port). The console port is used to physically connect (a PC or laptop) to the device.*
```bash
Switch(config)# line con 0
Switch(config-line)# password <password>
Switch(config-line)# login
```

7) Set a password for VTY (Virtual Terminal) and enables password verification at the virtual terminal login session :
- *The virtual terminal or “VTY” lines are virtual lines that allow connecting to the device using telnet or Secure Shell (SSH). Cisco devices can have up to 16 VTY lines. You can determine how many VTY lines you have by issuing “line vty 0 ?” from global configuration mode. The value 0 4 in this command means "from virtual terminal 0 to virtual terminal 4" because in this situation we assume that this switch can have only 5 user login to virtual terminal (telnet or SSH) at the same time. The device can allow 5 simultaneous virtual connections. By default five vty lines (0–4) are open.*
```bash
Switch(config)# line vty 0 4
Switch(config-line)# password <password>
Switch(config-line)# login
```

8) Encrypt the password :
- *This command **obscures all clear-text passwords in the configuration using a Vigenere cipher**.*
```bash
Switch(config)# service password-encryption
```

9) Set a login banner, known as the message of the day (MOTD) banner :
```bash
Switch(config)# banner motd #
```

10) Save the configuration :
- *This command save the running configuration to the startup file on non-volatile random access memory (NVRAM).*
```bash
Switch(config)# copy running-config startup-config
```

11) List all the IP interfaces or physical port and VLAN in the switch :
- *This command show the type (Fast Ethernet, Gigabit Ethernet, VLAN), IP address, status and protocol of the interface*
```bash
Switch# show ip interface brief
```
OR
```bash
Switch# sh ip int brief
```


## Router Configuration
1) Enter privilege mode :
```bash
Router> enable
```
OR
```bash
Router> en
```

2) Enter global configuration mode :
```bash
Router# configure terminal
```
OR
```bash
Router# config term
```

3) Disables the router from translating unfamiliar words (typos) into IP addresses :
```bash
Router(config)# no ip domain-lookup
```

4) Specifies the name for the router :
```bash
Router(config)# hostname <switch's name>
```

5) Set a password that is required for any user to enter global configuration mode :
```bash
Router(config)# enable secret <password>
```

6) Set a password for the console port of the router and enables password verification at the terminal login session :
- *Line con 0 refers to **the console port of the router** (it is usually either an RJ-45 or, on newer devices, a USB port). The console port is used to physically connect (a PC or laptop) to the device.*
```bash
Router(config)# line con 0
Router(config-line)# password <password>
Router(config-line)# login
```

7) Set a password for VTY (Virtual Terminal) and enables password verification at the virtual terminal login session :
- *The virtual terminal or “VTY” lines are virtual lines that allow connecting to the device using telnet or Secure Shell (SSH). Cisco devices can have up to 16 VTY lines. You can determine how many VTY lines you have by issuing “line vty 0 ?” from global configuration mode. The value 0 4 in this command means "from virtual terminal 0 to virtual terminal 4" because in this situation we assume that this switch can have only 5 user login to virtual terminal (telnet or SSH) at the same time. The device can allow 5 simultaneous virtual connections. By default five vty lines (0–4) are open.*
```bash
Router(config)# line vty 0 4
Router(config-line)# password <password>
Router(config-line)# login
```

8) Encrypt the password :
- *This command **obscures all clear-text passwords in the configuration using a Vigenere cipher**.*
```bash
Router(config)# service password-encryption
```

9) Set a login banner, known as the message of the day (MOTD) banner :
```bash
Router(config)# banner motd #
```

10) Save the configuration :
- *This command save the running configuration to the startup file on non-volatile random access memory (NVRAM).*
```bash
Router(config)# copy running-config startup-config
```

11) List all the IP interfaces or physical port of the router :
- *This command show the type (Fast Ethernet, Gigabit Ethernet, Subinterface, VLAN), IP address, status and protocol of the interface*
```bash
Router# show ip interface brief
```
OR
```bash
Router# sh ip int brief
```

## Reference :
- https://www.netwrix.com/cisco_commands_cheat_sheet.html
- https://www.cisco.com/c/en/us/td/docs/routers/access/800M/software/800MSCG/routconf.html
