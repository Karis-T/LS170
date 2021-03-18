## What to Focus On

> Understanding the role of the Transport layer is key to comprehending how networked applications communicate with each other. To develop a clear understanding, try to focus on the following areas.

#### Learn how transport layer protocols enable communication between processes

> Spend some time building a mental model for what multiplexing and demultiplexing are. Be clear about how ports work, along with IP addresses, to provide this functionality.

#### Learn that network reliability is engineered

> It's easy to think of 'the internet' as some abstract thing that just 'works'. One of the aims of this course is to peel away some of those layers of abstraction to show that the internet and the web are actually the combination of multiple technologies that have been designed and engineered. Network reliability is one aspect of that.

#### Understand the trade-offs

> As with any protocol or technology, TCP and UDP are the result of many different design decisions. Design decisions generally involve some sort of trade-off. Spend some time learning what TCP and UDP each provide, and what the trade-offs of each are.

## Transport Layer Summary

### Multiplexing

- ***Multiplexing*** and *demultiplexing* provide for the transmission of *multiple signals over a single channel*
- Multiplexing is enabled through the use of *network ports*

### Sockets

- Network sockets can be thought of as a *combination of IP address and port number*
- At the *implementation level*, sockets can also be *socket objects*

### Reliability

- The underlying network is *inherently unreliable*. If we want reliable data transport we need to implement a system of rules to enable it.

### TCP - Transmission Control Protocol

- *TCP* is a *connection-oriented* protocol. It establishes a connection using the *Three-way-handshake*
- TCP provides reliability through *message acknowledgement* and *retransmission*, and *in-order delivery*.
- TCP also provides *Flow Control* and *Congestion Avoidance*
- The main *downsides of TCP* are the *latency overhead of establishing a connection*, and the potential *Head-of-line blocking* as a result of in-order delivery.

### UDP - User Datagram Protocol

- *UDP* is a very simple protocol compared to TCP. It provides *multiplexing*, but no reliability, no in-order delivery, and no congestion or flow control.
- *UDP* is *connectionless*, and so doesn't need to establish a connection before it starts sending data
- Although it is unreliable, the *advantage of UDP* is *speed* and *flexibility*.