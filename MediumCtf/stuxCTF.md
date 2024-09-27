# Welcome to My  Solution: Watcher CTF

I am excited to share my solution for the **stuxCTF**. In this write-up, I'll walk you through the steps and techniques I used to complete this room on TryHackMe.

You can check out the room here: [stuxCTF](https://tryhackme.com/r/room/stuxctf).


## STEP 1: Enumerate the Target IP Address with Nmap
 
First we will use **Nmap** to enumerate the target IP address by running the following command:

```bash
nmap <ip> --min-rate=10000
```
From my nmap result i got 2 ports open 22 , 80

## Step 2 :  Directory Enumeration with Gobuster
```bash
gobuster dir -u <ip> -w /usr/share/wordlists/dirb/common.txt -x txt,php
```

i didnt got much information by this.

Now we can start looking over the website on port 80

After looking at source code we got some random value 
<!-- The secret directory is...
		p: 9975298661930085086019708402870402191114171745913160469454315876556947370642799226714405016920875594030192024506376929926694545081888689821796050434591251;
		g: 7;
		a: 330;
		b: 450;
		g^c: 6091917800833598741530924081762225477418277010142022622731688158297759621329407070985497917078988781448889947074350694220209769840915705739528359582454617;
		-->

After researching more about it we got that it is Diffie-Hellman key exchange cryptography!!

After decoding it using python script 
we got out third flag !!!
47315028937264895539131328176684350732577039984023005189203993885687328953804202704**********


