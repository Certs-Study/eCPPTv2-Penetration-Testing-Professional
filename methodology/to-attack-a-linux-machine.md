---
description: Methodology To Attack a Linux Machine
cover: ../.gitbook/assets/Methodology To Attack a Linux Machine.png
coverY: 266.431718061674
---

# 🟢 To Attack a Linux Machine

Ok after scanning the network we detect some Linux machines and now?&#x20;

What do we need to investigate in order to get root on the remote machine?

First scan all 65535 TCP ports available, don't scan them all at once. Start by scanning the most common ones then go increasing the port ranges.

Do the same for all 65535 UDP ports.

After scanning all ports we hope to find some services running on them, grab all banners from remote services, and investigate them.

The objective is to find services that can allow us to connect to the machine without authentication or send files to the machine, or a web server since it gives us a lot more to investigate in order to find an entry point.

If we don't find anything useful running on the host it's time to run different scans against the host. Remember don't be noisy, prepare yourself for the next exams.

### Juice Information

1. Linux Kernel version
2. The version of the Services running
3. Sometimes we can detect users remotely

### SSH Service

SSH is hard to exploit but can be brute forced, if you find a valid user try to brute force ssh.

Read more about [<mark style="color:red;">SSH Penetration Testing</mark>](https://www.poplabsec.com/ssh-penetration-testing/) here:

{% embed url="https://www.poplabsec.com/ssh-penetration-testing/" %}

{% content-ref url="http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/PQdYFP9mCxTDzSTiV7Ye/" %}
[SSH Penetration Testing](http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/PQdYFP9mCxTDzSTiV7Ye/)
{% endcontent-ref %}

### FTP Service

Old FTP can be an entry point into the remote system, maybe an anonymous user is allowed and we can get some files or better send files to the server.

Search for files inside the available folders in case you found a Web server folder send a PHP reverse shell.

Pay attention to hidden folders and the folder's names and paths as well.

FTP is nice to be brute-forced if you have a valid user. If you want to learn more about [<mark style="color:red;">**FTP Penetration Testing**</mark>](https://www.poplabsec.com/ftp-penetration-testing/) read my full article about it!

{% embed url="https://www.poplabsec.com/ftp-penetration-testing/" %}

### Samba Service

SMB is the most common entry point it has tons of CVEs and most of the time is poorly configured, Check my article about [<mark style="color:red;">SMB Penetration testing</mark>](https://www.poplabsec.com/smb-penetration-testing/) and learn how o breach it!

{% content-ref url="http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/97xPYP5fBC1HUB4v6ctp/" %}
[SMB Penetration Testing](http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/97xPYP5fBC1HUB4v6ctp/)
{% endcontent-ref %}

{% embed url="https://www.poplabsec.com/smb-penetration-testing/" %}

### DNS Service

{% content-ref url="http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/OpKVvhvkBWVTweXMg94K/" %}
[DNS Penetration Testing](http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/OpKVvhvkBWVTweXMg94K/)
{% endcontent-ref %}

### MySQL Service

{% content-ref url="http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/UnV09MwO7ZHfBNqQOCue/" %}
[MySQL Penetration Testing](http://127.0.0.1:5000/o/at4Z0L3dsguKUukMngZV/s/UnV09MwO7ZHfBNqQOCue/)
{% endcontent-ref %}

### Web Servers

Remember! Users from web applications are different from system users.

Read More about hacking Web Servers here:

{% embed url="https://hacking-webservers.popdocs.net/" %}
Hacking Web Servers
{% endembed %}

Read More about hacking Web Applications here:

{% embed url="https://hacking-web-applications.popdocs.net/" %}
Hacking Web Applications
{% endembed %}

### What do we want?

A stable highly privileged shell of course. Root access!

Transfer files to the machine.

Download files from the machine.

Pivoting into other networks.

