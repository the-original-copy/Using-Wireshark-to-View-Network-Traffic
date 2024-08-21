# Using-Wireshark-to-View-Network-Traffic

Table of Contents
=================

1 [Introduction](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic?tab=readme-ov-file#introduction)</br>
2 [Part 1: Capture and Analyze Local ICMP Data in Wireshark](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic?tab=readme-ov-file#part-1-capture-and-analyze-local-icmp-data-in-wireshark)</br>
3 [Part 2: Capture and Analyze Remote ICMP Data in Wireshark](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/blob/main/README.md#part-2-capture-and-analyze-remote-icmp-data-in-wireshark)</br>
4 [Conclusion](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/blob/main/README.md#conclusion)</br>

# Introduction

An application known as a packet sniffer or software protocol analyzer, Wireshark is used for network analysis, troubleshooting, software and protocol development, and teaching. The sniffer records each PDU as data streams pass across the network, allowing it to decode and examine its content in accordance with the relevant RFC or other guidelines.

## Part 1: Capture and Analyze Local ICMP Data in Wireshark

### Step 1: Retrieve my PC interface Address

Since I’m using ubuntu i used the command ip addr show to get my IP and MAC address as shown below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/b4cfb47a-392d-4133-8d45-393cc8440182)
<br/> Image 1: IP address is 192.168.100.96/24 while my MAC address is 80:91:33:0c:e9:c5 since I’m using the wireless interface(wlo1) to connect to the internet

</div>

Next I obtained my patner’s IP address as 192.168.100.96/24 since we are using the same wireless interface as shown in the picture below:

<div align="center">
  
![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/59720933-1097-4609-b2c7-a26fd1734c53)

</div>

### Step2: Start Wireshark and begin capturing Data

I navigated to the wireless interface wlo1 and applied the ICMP filter as shown below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/f2d8f969-4b36-4ee7-9ab7-64d186d66b14)

</div>

Next I pinged the other machine in the LAN and recieved the following feedback:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/f65cea01-7c99-47c1-a4df-2a66a1eddd0b)

</div>

In wireshark data did indeed start appearing abd below is the feedback I got:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/44b571ad-2be6-4acf-b966-8b0c7b8da418)

</div>

### Step 3: Examine the captured data

I clicked the first ICMP request and the feedback I got is as shown below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/d92600cb-0ed8-4af6-952d-cfaeac45a4e2)

</div>

Next I Expanded the ethernet2 section and indeed the source MAC address matches my PC’s address while the destination MAC address matches the team member’s MAC address as shown in the picture below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/b6baea88-614b-4e2c-a950-42727cde0c13)

</div>

Wireshark obtained the other machines MAC address by capturing the packets sent through the wireless interface and examining the frame’s header.

## Part 2: Capture and Analyze Remote ICMP Data in Wireshark
### Step 1: Start capturing data on the interface

I pinged www.yahoo.com and recieved the below feedback:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/dcdd6e0e-aafd-44ad-a7b6-9fd1112422f1)

</div>

Wireshark captured this ping and gave the following feedback:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/95476de9-dbad-4226-8355-f81158200fea)

</div>

I pinged www.cisco.com and got the following feedback:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/cc9becce-a031-4770-8353-5d513d0ed647)

</div>

Wireshark captured the following ping and returned the following result:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/b6c81f7c-2cd6-4dc3-9b48-33327f2a5e96)

</div>

I pinged www.google.com and got the below feedback:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/47d24a41-be3a-40d1-8156-ee1b375c79e2)

</div>

Wireshark captured this ping and returned the below feedback:

<div align=center>

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/b41beacb-3eaa-447d-8f62-38db7f41a4bd)

</div>

### Step 2: Examining and analyzing the data from the remote hosts

The IP address for www.yahoo.com is : 77.238.180.11
The MAC address for www.yahoo.com is : 90:3f:ea:b3:ba:2d
As shown below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/8924234c-ae80-4436-85c2-5d79bd6f6e41)

</div>

The IP address for www.cisco.com is : 2.17.169.15
The MAC address for www.cisco.com is : 90:3f:ea:b3:ba:2d
As shown below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/4b8a1b98-81bd-4964-9b6c-d87cbfeea605)

</div>

The IP address for www.google.com is: 142.251.209.4
The MAC address for www.google.com is: 90:3f:ea:b3:ba:2d
As shown below:

<div align="center">

![image](https://github.com/the-original-copy/Using-Wireshark-to-View-Network-Traffic/assets/77143082/b0b3131e-98cf-4ccb-8107-a1c860ada3b4)

</div>

The difference in the information received in the remote ping as compared to the local ping is the MAC address. In the local ping the destination address is described as Intel which is the company that made the NIC of the machine. In the remote ping all companies have the same MAC address which doesn’t make initiative sense meaning that there is a layer of abstraction that hides the true MAC address.

Wireshark knows the MAC address of local hosts since in a local network the packets used for communication contain both the source and destination MAC addresses since MAC addresses are used for communication in the data link layer.
For remote hosts, routers are used to enable communication and therefore they operate in the network layer where MAC addresses have already been stripped since they are not necessary.

# Conclusion

In conclusion, Wireshark is a flexible tool with a wide range of networking applications. Its capabilities as a packet sniffer and software protocol analyzer has enabled me to explore the nuances of networks, which is helpful for a variety of jobs, including software and protocol creation, network research and troubleshooting, and educational projects. Through the capture and decoding of data streams as they move over the network, Wireshark has enabled me to examine packet content according to industry standards like RFCs, offering critical insights that facilitate the comprehension of network behavior and the efficient resolution of problems. 

Interacting with the windows defender has also taught me how to interact with firewalls where I can add and subtract rules that affect the data that the computer can allow or deny.
