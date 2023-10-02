---
description: eCPPTv2 Enumeration process to attack all machines in your exam.
---

# 🟢 Enumeration

### SMB Enumeration



### NetBIOS Enumeration

#### NbtStat

```
nbtscan -v -s : 192.168.1.0/24
```

```
nbtscan -v 0.0.0.0 or 0.0.0.0/24
```

If we find a share we can mount, use:

```
sudo smclient mounts.cifs //RMT_IP//C /media/our_folder user=,pass=
```

#### Enum4Linux

```
enum4linux 192.168.1.64
```

```
#enum4linux -a -v 0.0.0.0
```

```
#net view 0.0.0.0 (windows cli) 
#net use
#mount command (linux)
#dumpsec (auditing tool for netbios- windows)

#rpcclient -N -U “” 0.0.0.0
#nat.exe userlist passlist ip
```

### SNMP Enumeration

#### SNMPWalk

```
snmpwalk -c public -v1 0.0.0.0 hrSWInstalledName
snmpwalk -v 2c -c public 0.0.0.0 hrMemorySize
snmpwalk -v 2c -c public 0.0.0.0 system.sysContact
snmpset -v 2c -c public 0.0.0.0 system.syscontact s new@els.com
snmkwalk -v 2c -c public 0.0.0.0 system.sysContact
```

#### NMAP SNMP Scripts

```
• snmp-brute
• snmp-info
• snmp-interfaces

```

```
• snmp-netstat
• snmp-processes
• snmp-sysdescr
• snmp-win32-services
```
