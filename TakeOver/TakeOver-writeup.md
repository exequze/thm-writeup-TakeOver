# TryHackMe - TakeOver
<p align="center">
  <img src="img/room-icon.png">
  <br>
  Room link : https://tryhackme.com/room/takeover<br>
  Difficulty : Easy<br>
</p>


## 1. Innitial Environment Setup

At first I mapped the target IP addres to the domain futurevera.thm within my /etc/hosts
<pre>
sudo bash -c 'echo "10.80.182.83    futurevera.thm" >> /etc/hosts'  
</pre>

Alternatively you can do sudo -s and then just the echo command.

## 2. Connectivity Check

I started with a simple ping to confirm the host was alive, followed by a standard Nmap scan

<pre>
┌──(exequze㉿kalimach)-[~]
└─$ ping 10.80.182.83
PING 10.80.182.83 (10.80.182.83) 56(84) bytes of data.
64 bytes from 10.80.182.83: icmp_seq=1 ttl=62 time=45.4 ms
64 bytes from 10.80.182.83: icmp_seq=3 ttl=62 time=43.6 ms
^C
--- 10.80.182.83 ping statistics ---
3 packets transmitted, 2 received, 33.3333% packet loss, time 2093ms
rtt min/avg/max/mdev = 43.626/44.488/45.351/0.862 ms
</pre>
33,3% packet loss, because I am too impatient and hit Ctrl + C.

<pre>
┌──(exequze㉿kalimach)-[~]
└─$ nmap 10.80.182.83
Starting Nmap 7.98 ( https://nmap.org ) at 2026-02-17 07:30 +0100
Nmap scan report for 10.80.182.83
Host is up (0.048s latency).
Not shown: 997 closed tcp ports (reset)
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
443/tcp open  https

Nmap done: 1 IP address (1 host up) scanned in 2.77 seconds
</pre>
As we can see, Ports 22, 80 and 443 are open.

## 3. Web Exploration & Rabbit-Hole
