# 🟢 Enumeration

### NetBIOS and Null Session

```
nmap -sS -p 135 <target>
```

**Probes NetBIOS info of machine:**

```
nbtscan -v <target>
```

**Displays system shares information:**

```
nmblookup -A <target>
```

**Lists all shared shares of target:**

```
smbclient -L <target>
```

**Enumerates information on target Windows system (shares, users, etc):**

```
enum4linux -a <target>
```

**Attempts to access a shared resources with no credentials (null session):**

```
smbclient \\\\<target>\\<share> -N
```

**Attempt to connect to RPC service with no credentials:**

```
rpcclient -N -U "" <target>
```

**Attempts to bruteforce SMB credentials with nmap:**

```
nmap --script=smb-brute <target>
```

### SNMP Enumeration

**Enumerates SNMP info of the given target:**

```
snmpwalk -c <c_string> -v <version> <target>
```

**Attempts to brute force SNMP community string:**

```
nmap -sU -p 161 --script=snmp-brute <target>
```

**Enumerate users:**

```
nmap -sU -p 161 --script snmp-win32-users <target>
```

**Lists all SNMP-related nmap scripts:**

```
ls -l /usr/share/nmap/script | grep -i snmp
```

**Obtains SNMP info at specified OID:**

```
snmpwalk -c <c_string> -v <version> <target> <OID>
```

**Changes the SNMP information at specified OID:**

```
snmpset -c <c_string> -v <version> <target> <OID> <value_type> <value>
```

**Onesixtyone brute force:**

```
echo public > community
echo private >> community
echo manager >> community
onesixtyone -c community <target>
```

**Enumerate system processes:**

```
snmpwalk -c <community string> -<version> <target> 1.3.6.1.2.1.25.1.6.0
```

**Enumerate running programs:**

```
snmpwalk -c <community string> -<version> <target> 1.3.6.1.2.1.25.4.2.1.2
```

**Enumerate processes path:**

```
snmpwalk -c <community string> -<version> <target> 1.3.6.1.2.1.25.4.2.1.4
```

**Enumerate storage units:**

```
snmpwalk -c <community string> -<version> <target> 1.3.6.1.2.1.25.2.3.1.4
```

**Enumerate software name:**

```
snmpwalk -c <community string> -<version> <target> 1.3.6.1.2.1.25.6.3.1.2
```

**Enumerate user accounts:**

```
snmpwalk -c <community string> -<version> <target> 1.3.6.1.4.1.77.1.2.25
```

**Enumerate tcp local ports:**

```
snmpwalk -c <community string> -<version> <target> 1.3.6.1.2.1.6.13.1.3
```

### SNMP and Metaespoit

```
msf > use auxiliary/scanner/snmp/snmp_login
msf > set PASSWORD public
msf > set RHOSTS file:snmp.txt
msf > set THREADS 25
msf > set VERBOSE false
msf > set VERSION 2c
msf > run
```

### NFS Enumeration

Discover rpcbind:

```
$ sudo nmap -sV --script rpcinfo 10.10.13.37 -p111
```

Run Nmap scripts:

```
$ sudo nmap -sV --script 'nfs*' 10.10.13.37 -p2049
```

## Mount

```
$ showmount -e 10.10.13.37
$ sudo mount -v -t nfs -o vers=3 -o nolock -o user=snovvcrash,pass='Passw0rd!' 10.10.13.37:/home /mnt/nfs
```

{% embed url="https://resources.infosecinstitute.com/exploiting-nfs-share/" %}
