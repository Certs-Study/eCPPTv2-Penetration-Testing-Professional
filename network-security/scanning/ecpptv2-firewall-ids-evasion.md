# 💚 eCPPTv2 - Firewall IDS Evasion

1. Fragmentation
2. Decoys
3. Timing
4. Source Ports

### Nmap Fragmentation

```
nmap -sS -f [TargetIP]
```

```
nmap --mtu [mtuNumber] [TargetIP] -p [TargetPort]
```

### Nmap Decoys

```
nmap -sS -D [DecoyIP#1],[DecoyIP#2] .. [DecoyIP#N], ME [TargetIPde
```

```
nmap -D RND:[Number] [TargetIP] 
```

### Nmap Timing Attacks

### Nmap Source Ports
