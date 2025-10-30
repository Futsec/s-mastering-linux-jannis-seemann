<div align="center">                                                                                                    
    <h1>Networking<br>Cheatsheet</h1>                                                                            
    <p>                                                                                                                 
        <em>Arrange and Manage Linux Communication Channels</em>
    </p>                                                                                                                
</div>                                                                                                                  

<br>                                                                                                                    
<br>

## Table of Contents

1. [What is the Internet](#what-is-the-internet)
2. [The IP Command](#the-ip-command)
3. [The tool Wireshark](#the-tool-wireshark)
4. [The Open Systems Interconnection (OSI) Model](#the-open-systems-interconnection--osi--model)

<br>
<br>

### What is the Internet

The _internet_ is a network of networks, an interconnected set of nodes which form a mesh and are able to communicate 
with each other. We can build a connection with pretty much any other computer on a network, without having a dedicated 
connection to the device. We do this through the use of packets which gets assigned an IP address.

<br>

### The IP Command
#### Inspecting Network Configurations

|Command|Description|Example|
|:---|:---|:---|
|`ip`|A powerful CLI tool for managing and diagnosing network configurations, also used to inspect and modify IP Address, routes and network interfaces. This is replaces the older `ifconfig`, `route` & `netstat` commands, as it can be used on more complex networks.|[View](#ip)|


#### ip
```sh
    ip addr show                                 # View our own network
     ↪ replaces ifconfig -a
```

<br>

### The tool Wireshark
#### Monitoring Network Traffic

Although Wireshark is a GUI application, we still use it as it displays a lot of useful information. Wireshark is a 
powerful network tool, which can intercept, monitor and analyze network traffic. Its important to not that this is 
illegal to or use on networks that do not belong to you.

Wireshark might capture sensitive information that is transmitted through the network. Deppending on where are based, 
the laws might be different. In some cases using Wireshark ethically is not a problem. These erhical use cases range 
from learning, teaching, ethical hacking, as long as you are not logging private information of others.

If you living alone, all your devices should be yours and should in this case be legal to use wireshark. Though if you 
living  with someone else, always ask for permission and or ask a network administrator for permission to use Wireshark.
Also consider checking the laws in your country before using Wireshark.

We can use Wireshark by installing it using `apt` and then running Wireshark with sudo privileges, as it needs elevated 
privileges in order to capture some information.

#### Steps for installing and use

1. `sudo apt install wireshark`
2. `sudo wireshark` 

<br>

### The Open Systems Interconnection (OSI) Model

As we already know the OSI model is a conceptual model, its used for understanding and designing computer networks. It
standardizes the functions and protocols across various different devices.

#### The OSI Model
 
<div align="center">
    <p>
        <strong>P</strong>lease <strong>D</strong>o <strong>N</strong>ot <strong>T</strong>hrow <strong>S</strong>ausage <strong>P</strong>izza <strong>A</strong>way
    </p>
</div>

|Layer Number|Layer                              |Short Description|
|:----------:|:----------------------------------|:----------------|
|7           |**Application Layer**<br>_Layer 7_ |Provides the interface for applications to communicate over the network.<br> ↪ **HTTP**, **FTP**, **SMTP**|
|6           |**Presentation Layer**<br>_Layer 6_|Translates, encrypts and compresses data for transmission between applications and networks.<br> ↪ **TLS/SSL**|
|5           |**Session Layer**<br>_Layer 5_     |Manages and controls the establishment, maintenance and termination of sessions between applications.|
|4           |**Transport Layer**<br>_Layer 4_   |Ensures reliable data between hosts<br> ↪ **TCP**, **UDP**|
|3           |**Network Layer**<br>_Layer 3_     |Manages data routing and forwarding between networks.<br> ↪ **IP Address**, **Routers**|
|2           |**Data Link Layer**<br>_Layer 2_   |Provies error-free data transfer between adjacent network nodes.<br> ↪ **Ethernet**, **MAC Address**|
|1           |**Physical Layer**<br>_Layer 1_    |Handles the transmission of raw data bits over a physical medium.<br> ↪ **Cables**, **Switches**, etc...|

<br>

<div align="center">
    <img src="../../assets/imgs/cheatsheats/networking_cs/osi_model.png" alt="Diagram of the OSI model">
</div>

<br>







