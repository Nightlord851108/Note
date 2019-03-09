# TCP/IP

## TCP/IP Model
It's a concise version of OSI model. TCP/IP model contains four layers, instead of seven layers in OSI model.
1. [Network Access/Link layer](#network-access-layer): Cover data-link and physical layer in OSI model. It's the method to transfer a packet from the internet layer of one machine to the internet layer of another.
2. [Internet layer](#internet-layer): Cover network layer in OSI model. To transmit a packet through network.
3. [Host-to-Host/Transport layer](#transport-layer): Cover transport layer in OSI model. To solve if the data to transport arrived, and whether the sequence of data arrived is correct problems.
4. [Protocol/Application layer](#application-layer): Cover application, presentation, and session layers in OSI model. A layer for applications to communicate through internet.

### TCP/IP vs OSI
![TCP/IP model vs OSI model](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/tcpAndOSI.png)

|        TCP/IP        |        OSI        |
|----------------------|-------------------|
|TCP refers to Transmission Control Protocol. | OSI refers to Open Systems Interconnection.|
|      4 layers.       |      7 layers     |
|    more reliable     |   less reliable   |
|does not have very strict boundaries | has strict boundaries|
|follow a horizontal approach | follows a vertical approach|
|uses both session and presentation layer in the application layer itself | uses different session and presentation layers|
| developed protocols then model | developed model then protocol|

---


### Network Access Layer
This layer corresponds to the combination of Data Link Layer and Physical Layer of the OSI model.It looks out for hardware addressing and the protocols present in this layer allows for the physical transmission of data.

### Internet Layer
This layer parallels the functions of OSI’s Network layer. It defines the protocols which are responsible for logical transmission of data over the entire network.

The main protocols residing at this layer are :
1. **IP**: Responsible for delivering packets from the source host to the destination host by looking at the IP addresses in the packet headers.

2. **ICMP**: stands for Internet Control Message Protocol. It is encapsulated within IP datagrams and is responsible for providing hosts with information about network problems.

3. **ARP**: stands for Address Resolution Protocol. Its job is to find the hardware address of a host from a known IP address. ARP has several types: Reverse ARP, Proxy ARP, Gratuitous ARP and Inverse ARP.

## Transport Layer
This layer is analogous to the transport layer of the OSI model. It is responsible for end-to-end communication and error-free delivery of data. It shields the upper-layer applications from the complexities of data.

The two main protocols present in this layer are :

|  TRANSMISSION CONTROL PROTOCOL (TCP)  |  USER DATAGRAM PROTOCOL (UDP)  |
|---------------------------------------|--------------------------------|
|TCP is a connection-oriented protocol. The communicating devices should establish a connection before transmitting data and should close the connection after transmitting the data. | UDP is the Datagram oriented protocol. There is no overhead for opening a connection, maintaining a connection, and terminating a connection. UDP is efficient for broadcast and multicast type of network transmission.|
|TCP is reliable as it guarantees delivery of data to the destination router. | The delivery of data to the destination cannot be guaranteed in UDP.|
|provides extensive error checking mechanisms. <br/>It is because it provides flow control and acknowledgment of data. | only the basic error checking mechanism using checksums|
| packets arrive in-order at the receiver | If ordering is required, it has to be managed by the application layer. |
| comparatively slower than UDP | faster, simpler and more efficient than TCP |
|Retransmission of lost packets is possible | No retransmission of lost packets|
| 20-byte header size | 8-byte header size |
| heavy-weight | lightweight |
| used by HTTP, HTTPs, FTP, SMTP and Telnet | used by DNS, DHCP, TFTP, SNMP, RIP, and VoIP. |

## Application Layer
This layer performs the functions of top three layers of the OSI model: Application, Presentation and Session Layer.

Some of the protocols present in this layer are: HTTP, HTTPS, FTP, TFTP, Telnet, SSH, SMTP, SNMP, NTP, DNS, DHCP, NFS, X Window, LPD
