# 🟢 Filters

**Filter packets by IP**

```
ip.addr==<ip>
```

**Filter packets sent from a specific address**

```
ip.src==<ip>
```

**Specify destination IP**

```
ip.dst==<ip>
```

**Filter traffic by request method**

```
http.request.method == POST
```

**Filter ARP traffic**

```
arp
```

**Filter HTTP traffic**

```
http
```

**Filter ICMP traffic**

```
icmp
```

**Filter HTTP or DNS traffic**

```
http or dns
```

**Filter HTTP or DNS traffic coming from specific address**

```
ip.addr==<ip> and (dns or http)
```

**Don't capture HTTP traffic from a specific IP**

```
http and ip.src!=<ip>
```

**Filter traffic from specific tcp port**

```
tcp.port==<port>
```

**Filter traffic from specific udp port**

```
udp.port==<port>
```

**Capture packets with SYN flag enabled**

```
tcp.flags.syn==1
```

**Capture packets with SYN and ACK**

```
tcp.flags.syn==1 and tcp.flags.ack==1
```

**Capture packets with SYN and ACK inside a subnet**

```
tcp.flags.syn==1 and tcp.flags.ack==1 and ip.addr==192.168.1.0/24
```

**Filter packets by string**

```
tcp contains "string"
```
