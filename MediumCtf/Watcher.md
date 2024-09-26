# Welcome to My First Solution: Watcher CTF

I am excited to share my solution for the **Watcher CTF**. In this write-up, I'll walk you through the steps and techniques I used to complete this room on TryHackMe.

You can check out the room here: [Watcher CTF](https://tryhackme.com/room/watcher).

## Step 1: Enumerate the Target IP Address with Nmap

First, we will use **Nmap** to enumerate the target IP address. Run the following command:

```bash
nmap <ip> --min-rate=10000
```

From the Nmap results, we found three open ports: HTTP, SSH, and FTP.

## Step 2: Directory Enumeration with Gobuster

```bash
gobuster dir -u <ip> -w /usr/share/wordlists/dirb/common.txt -x txt,php
```
