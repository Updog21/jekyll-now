---
layout: post
title: psSense online gaming matchmaking issues - NAT type
---
After the pfSense deployment everything was working great. Eventually though  one of my housemates said he could no longer find Street Fighter V matches online (PC), and my other housemate said his NAT type was strict on CoD, and couldn't join his friend's lobbies. This is because the pfSense default Automatic Outbound NAT mode re-writes the source port when peforming NAT which is okay for most applications, but for applications like online games it can cause issues. I didn't want to use a DMZ, although I may in the future, so for now the Hybrid-Outbound NAT mode with a mapping in place for each device will suffice, and preserve their source ports.

###Solution

1. Create static IP for the gaming device, in this case its a PC
2. Enable UPnP & NAT-PMP ( I had it already enabled )
..*Enable Default Deny
..*Add an ACL entry for the IP  "allow 53-65535 (static IP)/32 53-65535"
3. Add NAT rule for 

