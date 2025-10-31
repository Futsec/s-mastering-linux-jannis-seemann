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
5. [Layer 1, The Physical Layer](#layer-1-the-physical-layer)
6. [Layer 2, The Data Link Layer](#layer-2-the-data-link-layer)


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
    <img src="../../assets/imgs/cheatsheets/networking_cs/osi_model.png" alt="Diagram of the OSI model">
</div>

<br>

### Layer 1, The Physical Layer

The physical layer is what is referred to as the physical medium. This being copper cables, fibre optic cables and 
wireless among other things. It is responsible for converting digital data to signals, as well as converting signals 
back to digital data. Basically, layer 1 is a medium by which its able to send bits, or electrical signals.

#### How would we influence a layer 1 or physical layer?
We can do this by either switching off the hardware, or by unplugging the cable from the device physically, or through 
the use of software. To do this through the use of software, we first need to find the device name we want to influence.

We can find this out by using `ip addr show`, and this is an example of the output.

```sh
    1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
        link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
        inet 127.0.0.1/8 scope host lo
           valid_lft forever preferred_lft forever
        inet6 ::1/128 scope host 
           valid_lft forever preferred_lft forever
    2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
        link/ether 02:42:ac:11:00:02 brd ff:ff:ff:ff:ff:ff
        inet 192.168.1.10/24 brd 192.168.1.255 scope global dynamic eth0
            valid_lft 86399sec preferred_lft 86399sec
        inet6 fe80::42:acff:fe11:2/64 scope link 
            valid_lft forever preferred_lft forever
    3: wlan0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
        link/ether 00:1a:2b:3c:4d:5e brd ff:ff:ff:ff:ff:ff
```

- `lo` &rarr; loopback interface.
- `eth0` &rarr; wired Ethernet interface with IPv4 and IPv6 addresses.
- `wlan0` &rarr; wireless interface (currently down).


```sh
    ip addr show
    ip link set dev [device] down                # Turn device off through software, placing it into sleep mode.
     ↪ ip link set dev [device] up               # Turn device on, taking it out of sleep mode.
```

<br>

### Layer 2, The Data Link Layer

Once we have established a physical connection, we need a way to define who should receive the data. The data link 
layer is responsible for sending frames to specific devices, it does this through frame encapsulation, _its counter part
being decapsulation_. However, this is where **Logical Link Control** (_LLC_) and **Media Access Control** (_MAC_) comes
into play.

**LLC** is the interface between the Data Link Layer and the Network Layers. **MAC** gives us a way to identify the 
sender and receiver of a frame. **Frame Encapsulation** is the organizing of data into frames for transmission, as well
as adding the source and destination MAC address.

Some common protocols that run on the Data Link Layer, are **Ethernet**(_IEEE802.3_) & **WiFi**(_IEEE802.11_).

**Ethernet** or _IEEE802.3_ is a family of network technologies mostly used in LAN (Local Area Network). Ethernet splits 
the data into frames. A frame is usually maxed at 1.5kb in size. It contains the actual data that we want to transfer, 
as well as a checksum, so the destination can verify if it has received the data correctly.

It also contains addressing information, such as the MAC source and MAC destination.

**WiFi** or _IEEE802.11_ is a wireless networking protocol. The frames are identical to that of ethernet, but with WiFi
having extra data attach to identify the wireless connection. Still both **Ethernet** & **WiFi** are highly compatible 
with each other.

#### What exactl is a MAC Address?

The MAC address is a unique idenfier for network interfaces. Its a 48 bit (_6 byte_) split within 6 groups of 2 
hexadecimal digits, seperated by colons, e.g. `01:23:45:67:89:AB`. You can further break up the MAC Address between
**OUI** and **DSI**, Where the first 3 groups are the OUI and the last 3 groups DSI.

The MAC Address doesn't identify the computer itself, but the network interface card.

<br>

<div align="center">
    <img src="../../assets/imgs/cheatsheets/networking_cs/mac.png">
</div>

<br>

#### Understanding Layer 2 Hardware, Bridges, Switches and Wireless Access Points.

Typical hardware for this layer are:

- Bridge
- Switchings (_Ethernet_)
    - ↪ _Some switches may also work on Layer 3_.
- Wireless Access Points
    - ↪ This is completely different from a wifi router, Where as a wireless access point only works on layer 2.

<div align="center">
    <img src="../../assets/imgs/cheatsheets/networking_cs/layer_2_hardware.png">
</div>

<br>

### Layer 3, The Network Layer

With layer 2 or Data Link Layer, we could only send frames from one computer to another if the devices were connected 
directly to each other. If the computers were not directly connected, we would not have been able to send messages 
through layer 2, This is where the network layer comes into play.

Here we can send packets that can be routed to other networks, whereby **routing** refers to a packet being forwarded.
The idea is we no longer work with the MAC addresses but with IP addresses. Those packets can be forwarded to other 
networks.

#### What is a network?

A network is a group of interconnected devices that can communicate and share resources. Said devices can include 
computers, servers, printers, routers, switches and more. 

There are various types of networks:

- **PAN** _Personal Area Network_
- **LAN** _Local Area Network_
    - ↪ **WLAN* _Wireless Local Area Network_
- **CAN** _Campus Area Network_
- **MAN** _Metropolitan Area Network_
- **WAN** _Wide Area Network_
    - **WWAN** _Wireless Wide Area Network_
- **VPN** _Virtual Private Network_
- **GAN** _Global Area Network_

<br>

<div align="center">
    <img src="../../assets/imgs/cheatsheets/networking_cs/network_overview.png">
</div>

<br>

#### How can we inspect this information

We can use `ip addr show` to view our IP address information, or `ip route show` to view the route it would take within
out network.

#### What is a subnet?

A subnet is a network within a network, allowing us to manage more computers at the same time, making large networks 
more efficient. At home out network is a subnet of the internet, while in a corporate setting we can split out  
corporate network into multiple subnets and increase the efficiency.

A **Subnet Mask** is what allows us to do this, its how we can differentiate if an IP is part of out network or another
network. A subnet mask is usually represented as `255.255.255.0` or in a short hand way, `192.168.1.2/24`.

For example is you had the following address:
- IP Address
    - 192.168.1.2
- Subnet Mask
    - 255.255.255.0

This would be represented in binary as:
- IP Address
    - 1100000.10101000.00000001.00000010
- Subnet Mask
    - 11111111.11111111.11111111.0000000

<br>

<div align="center">
    <img src="../../assets/imgs/cheatsheets/networking_cs/subnet_mask.png"
</div>

<br>

> ❗ **NOTE**: _An IP of 192.168.1.0 is used for the gateway, while 192.168.1.255 is used for broadcasting on the network._
