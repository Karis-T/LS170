## What to focus on

#### Build a general picture of the network infrastructure

> Networking is a deep topic, and there's much of it that we purposely don't cover here. We don't expect you to memorize every single detail of how things work at this level, that's the domain of network engineering. As a developer or software engineer, it helps to have a high-level picture of how the underlying infrastructure functions. Much of the specific detail isn't necessary. The idea instead is to build the general mental models that will provide sufficient context to understand protocols operating at higher levels of abstraction, such as TCP and HTTP. If there's a topic that we don't mention or don't elaborate on too deeply, it's because you don't need to learn it right now.

#### Be aware of the limitations of the physical network

> Higher-level protocols, such as TCP and HTTP, rely on the underlying network infrastructure in order to function. As such, they are bound by the limitations of that infrastructure, such as network bandwidth and latency. Understanding these limitations provides important context when learning about those protocols.

#### Understand that protocols are systems of rules

> The protocols that support network functionality are essentially logical sets of rules that have been designed and engineered to be the way they are. Viewing them as such makes them easier to break down and contextualize.

#### Learn that IP enables communication between devices

> The Internet Protocol (IP) is a key part of the functionality of the internet. Make sure to form a clear mental model of what it does.

## Summary

### Terminology 

- The **internet** is a vast *network of networks*. It is comprised of both the *network infrastructure* itself (devices, routers, switches, cables, etc) and the *protocols* that enable that infrastructure to function.

- **Protocols** are *systems of rules*. Network protocols are systems of rules governing the exchange or transmission of data over a network.

- Different types of protocol are concerned with different aspects of network communication. It can be useful to think of these different protocols as operating at particular **'layers'** of the network.

- ***Encapsulation*** is a means by which protocols at different network layers can work together.

- Encapsulation is implemented through the use of ***Protocol Data Units* (PDUs)**. The PDU of a protocol at one layer, becomes the data payload of the PDU of a protocol at a lower layer.

  ### The Physical Layer

- The *physical network* is the tangible infrastructure that transmits the electrical signals, light, and radio waves which carry network communications.

  - *Latency is a measure of delay*. It indicates the amount of time it takes for data to travel from one point to another.
  - *Bandwidth is a measure of capacity*. It indicates the amount of data that can be transmitted in a set period of time.

### The Data Link Layer
- *Ethernet* is a set of standards and protocols that enables *communication between devices on a local network*.
  - Ethernet uses a Protocol Data Unit called a Frame.
  - Ethernet uses *MAC addressing* to identify devices connected to the local network.

### The Internet Layer

- The *Internet Protocol* (IP) is the predominant protocol used for *inter-network communication*.
  - There are two versions of IP currently in use: IPv4 and IPv6.
  - The *Internet Protocol* uses a system of addressing (IP Addressing) to *direct data between one device and another across networks*.
  - IP uses a Protocol Data Unit called a Packet.