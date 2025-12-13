---
layout: post
title: Honeypot and ASCII Cats
image: /assets/images/noodle.jpg
tags:
  - honeypot
  - SSH brute force attack
  - hacker psychology
author: Yuchan
type: Personal Project
organization: Mass Cybersecurity Center 
location: Tufts University, Medford, MA
comments: true
---

## Description
To explore real-world cyberattacks, I built a honeypot by launching servers with AWS. Moreover, to explore hacker psychology, I placed cat illustrations made with ASCII characters in the files as content to see hackers' reactions. My first server was attacked in the first week of being set up. I then enhanced the defense on the server by turning down the reaction to Ping, moving SSH to port 2222, and adding a VPN in front of the server.

## My Role
This is an independent project.

## Highlights

- Building the Honeypot  
I launched a server with AWS. I set a security rule that SSH only allows my IP address. I also used Amazon CloudWatch to monitor the activities of the server, including inbound and outbound network.

On the terminal, by logging into the server, I confirmed that the firewall, SSH, and Ping functionalities were working. The server login attempts are monitored with /var/log/auth.log and command lines are monitored with ./bash_history.

Lastly, I set up the ASCII art in the files.

- Attack Occurrence X_X  
On November 17, 2024, I noticed the SSH port was closed and the server was not accessible. After checking the monitoring status, I noticed that there had been 3.5GB of inbound network traffic on the server on November 13. After investigating, I determined it was an SSH brute-force attack. 

![SSHclosed]({{ "/assets/images/sshclosed.jpg" | relative_url }})
![inboundnetwork]({{ "/assets/images/inboundnetwork.jpg" | relative_url }})

- Post Attack  
I then launched a new server with stronger protection. I disabled ping responses, moved SSH to port 2222, and added a VPN in front of the server. The new server continues to receive unknown inbound network traffic, but nothing fatal.

![newserver]({{ "/assets/images/newserver.jpg" | relative_url }})

- ASCII cats  
Unfortunately, this component of the research failed because I was not able to access the server after the attack. However,I learned that large-scale attacks are more likely to be conducted by botnet machines instead of humans.

![A cute ASCII cat]({{ "/assets/images/hi.jpg" | relative_url }})
![A cute ASCII cat]({{ "/assets/images/cappuccino.jpg" | relative_url }})
![A cute ASCII cat]({{ "/assets/images/spa.jpg" | relative_url }})
![A cute ASCII cat]({{ "/assets/images/noodle.jpg" | relative_url }})
![A cute ASCII cat]({{ "/assets/images/sleepy.jpg" | relative_url }})
![A cute ASCII cat]({{ "/assets/images/vocation.jpg" | relative_url }})

## Outcome
Presentation powerpoint can be found here:
[honeypot presentation (PDF)]({{ "/assets/honeypot.pdf" | relative_url }})

