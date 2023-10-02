---
description: eCPPTv2 host discovery techniques.
---

# 🟢 Host Discovery

### **Before a SYN scan with wihtout arp ping:**

```
nmap -sn <target> --disable-arp-ping
```

### **Before a SYN scan with wihtout arp ping and with TCP packet with a SYN flag attached:**

```
nmap -sn -PS <target> --disable-arp-ping
```

### **Before a SYN scan with wihtout arp ping and with TCP packet with a ACK flag attached:**

```
nmap -sn -PA <target> --disable-arp-ping
```

### **Before a SYN scan with wihtout arp ping and with TCP packet with ICMP echo request:**

```
nmap -sn -PE <target> --disable-arp-ping
```

### **Send ICMP ech**o request packets an**d only display hosts that are alive:**

```
fping -A <target>
```



**Send ICMP echo request packets and only display hosts that are alive and specify the number of retries (-r):**

```
fping -A <target> -r <number of retries>
```

Specify a range of ip addresses such as a whole subnet (-g), send ICMP packets to every host in subnet, display time required to reach host (-e) and force fping to be quiet (-q):

```
fping -q -a -g <target> <subnet to scan> -r 0 -e
```
