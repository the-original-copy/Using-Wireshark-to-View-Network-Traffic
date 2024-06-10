# Using-Wireshark-to-View-Network-Traffic

# Introduction

An application known as a packet sniffer or software protocol analyzer, Wireshark is used for network analysis, troubleshooting, software and protocol development, and teaching. The sniffer records each PDU as data streams pass across the network, allowing it to decode and examine its content in accordance with the relevant RFC or other guidelines.

## Part 1: Capture and Analyze Local ICMP Data in Wireshark

## Step 1: Retrieve my PC interface Address

Since I’m using ubuntu i used the command ip addr show to get my IP and MAC address as shown below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/b4cfb47a-392d-4133-8d45-393cc8440182)
<br/> Image 1: IP address is 192.168.100.96/24 while my MAC address is 80:91:33:0c:e9:c5 since I’m using the wireless interface(wlo1) to connect to the internet

</div>







