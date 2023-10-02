---
description: >-
  Methodology To Scan a Network on a Penetration testing assessment, understand
  what to do without triggering IDS alarms.
cover: ../.gitbook/assets/Methodology  To Scan a Network.png
coverY: 257.97356828193836
---

# 🟢 To Scan a Network

Usually on certifications labs or execuing a pentestration test on a client we have define in our scope a sub net with specified range of IPs.

Before start scanning the network I usually execute some commands on my machine to verify what interface is associated with the VPN to verify my IP and verify my ARP table.

### What to expect?

Networks can filter types of traffic or traffic to specific port numbers. Pay attention if you trying to get a reverse shell on a random port number, that port could be blocked.

### What if the Network is blocking some types of traffic?

As I said networks can filter types of traffic like TCP/UDP/SCTP/ICMP or even IP, yes IP!&#x20;

Most of corporate networks block all traffic and only allow a tunnel between two endpoints validating src IP and dst IP, protocol type and service/port.

UDP traffic can be block only for a specific host and allowed for other inside the same subnet.&#x20;

Or can be blocked on all subnet like IPv6.

In these case we need to test the network for each host we've found.

### Detect Hosts using Layer 2 - ARP

In order to detect hosts on our network without trigger alot of IDS alarms we can use the ARP command. We will send ARP requests to the network and wait for all responses&#x20;

### Detect Hosts using Layer 3 - IP / ICMP

We can use ping command send ICMP packets and verify if the host is alive but remember some hosts are configured to not response to ICMP ECHOs.

to scan using the IP protocol we can use nmap.

### Detect Hosts using Layer 4 - TCP/UDP

What if we can't connect to any port using any protocol? or at least any port we test was



### Traceroute is our Friend!

Traceroute using TCP

```
sudo traceroute -T 192.168.4.5
```

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Traceroute using UDP

```
sudo traceroute -U 192.168.4.5
```

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### Traceroute using ICMP

```
sudo traceroute -I 192.168.4.5
```

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

### Keep in Mind

You need to develop you attacking methodology here I only talk about basics steps. Ping me on Discord to talk about other techniques. I will love it!
