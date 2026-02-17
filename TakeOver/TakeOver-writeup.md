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

I started with a simple ping to confirm the 
