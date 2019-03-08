# OSI Model

OSI Model is a conceptual model which characterizes the communication between two devices in a telecommunication or computer system.

There are 7 layers in OSI model:
1\. [Physical layer](#physical-layer)
2\. [Data link layer](#data-link-layer)
3\. [Network layer](#network-layer)
4\. [Transport layer](#transport-layer)
5\. [Session layer](#session-layer)
6\. [Presentation layer](#presentation-layer)
7\. [Application layer](#application-layer)

## Physical Layer

Physical layer is responsible for send and receive data between two devices with a physical transmission medium.

## Data link layer

Data link layer provides node-to-node data transfer. It detects and possibly corrects errors that may occur in physical layer. It defines protocol to establish and terminate the connection between two physical devices.

**Flow Control**: It's a process rate control of a transmission between two nodes to prevent a fast sender from overwhelming slow sender. It provides mechanism for receiver to control the transmission speed.

-   **Medium access control(MAC)**: Responsible for controlling how devices in a network gain access to a medium and permission to transmit data.
-   **Logic link control(LLC)**: Responsible for identifying and encapsulating network protocols, and controls error checking and frame synchronization.

## Network layer

The network layer provides the functional procedural means of transferring variable length of packets from one node to another connected in **different networks**.
