# Internet Protocol

## IPv4
IPv4 is a connectionless protocol used for **packet switched** networks.

IPv4 uses 32-bit (4 byte) addressing, which gives 232 addresses.

## IPv6
IPv6 is 128-bits address having an address space of 2^128, which is way bigger than IPv4.

In IPv6 we use Colon-Hexa representation. There are 8 groups and each group represents 2 Bytes.
![IPv6 Format](http://contribute.geeksforgeeks.org/wp-content/uploads/ipv6-1-2-1024x284.png)

In IPv6 representation, we have three addressing methods :
* **Unicast Address**: Unicast Address identifies a single network interface. A packet sent to unicast address is delivered to the interface identified by that address.

* **Multicast Address**: Multicast Address is used by multiple hosts, called as Group, acquires a multicast destination address. These hosts need not be geographically together. If any packet is sent to this multicast address, it will be distributed to all interfaces corresponding to that multicast address

* **Anycast Address**: Anycast Address is assigned to a group of interfaces. Any packet sent to anycast address will be delivered to only one member interface (mostly nearest host possible).

Note : Broadcast is not defined in IPv6.


## Difference between IPv4 and IPv6

|           IPv4           |           IPv6           |
|--------------------------|--------------------------|
|32-bit address length     |128-bit address length    |
|Supports Manual and DHCP address configuration | End to end connection integrity Achievable |
|generate 4.29×109 address space | produce 3.4×1038 address space|
|Security future is dependent on application | IPSEC is inbuilt security future |
| Address representation in decimal | Address representation in hexadecimal |
| Fragmentation performed by Sender and forwarding routers | fragmentation performed only by sender|
| Packet flow identification is not available | Packet flow identification are Available and uses flow label field in the header|
| checksum field is available | checksum field is not available |
| Broadcast Message Transmission Scheme | multicast and any cast message transmission scheme is available|
| Encryption and Authentication facility not provided | Encryption and Authentication are provided|
