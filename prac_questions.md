## The Internet

1. **What is the internet? How does it work?**

   - The internet is a network of networks.
   - Essentially a network is 2 devices connected in order to communicate and exchange data. (eg 2 computers joined together via a LAN cable & configuring their settings to form a network)
   - LAN Networks connected to hubs or switches are only limited to the devices that are connected, that is they have geographic limitations. 
   - To join networks to other networks and span larger distances we use routers. Routers divert network traffic to other networks. They're like gateways in and out of the network.
   - These smaller networks connected to other networks via routers essentially is what makes up the internet. 
   - Despite their differences many kinds of devices, brands, models are all connected to the internet thanks to protocols. Protocols are a system of rules in place so data can be exchanged between these different components.
   - Different protocols either address the same aspect of communication (TCP & UDP both transfer messages between applications but just in different ways) Or address different aspects of communication altogether (HTTP structures messages between apps TCP transfers them)
   - Because the internet is so complex we can split each aspect of the internet up into layered system and focus on each layer one at a time.
   - Two models attempt to solve this problem. The OSI (Open systems interconnection) Model and the TCP/IP (Internet Protocol Suite) model. It's important to note that these models are only references and do not fit a real world scenario. They're useful for an overview of how the system works as a whole and aid in dividing up the levels of responsibility of the internet. 
   - OSI layers are divided up into functions  (physical addressing, logical addressing and routing, encryption, compression, etc).
   - TCP/IP layers are divided up into communication scope (within a local network, between networks, etc)
   - Both models implement data encapsulation- That is they hide data from one layer by encapsulating it within the data of another layer. The protocol of one layer doesn't need to know how protocols of other layers operate. Each layer provides a service to the layer above it. This is done with PDU's or Protocol Data Units.
   - PDU's are a block of Data transmitted over the network. Each layer refers to a PDU by a different name. Basically though a PDU consists of a header, a data payload and sometimes a trailer. 
   - Headers and trailers purpose is to provide protocol meta data about a PDU. eg. Source and destination IP addresses used to route the packet.
   - data payload's use a protocol at a specific layer to transport the requested data over the network.

2. **What are the characteristics of the physical network?** 

   - The physical network is made up of physical components including cables, devices and wires which transmit binary data as signals, light and radio waves.  This system is bound by physical laws.
   - These laws explain the real world limits of how data is transported from one place to another. eg how fast an electrical signal of light can travel, distance a radio wave can reach etc.
   - these limitations determine the physical characteristics of networks and impact how upper layer protocols function.
   - 2 main characteristics of the physical network are latency and bandwidth.

3. **What is latency? Explain the 4 types of latency**

   - Latency is a measurement of delay. Data from one location and point in time reaches its destination at a later point in time. Delay is the difference between these 2 points in time.
   - There are several types of delay that determine the overall latency in a network connection. The sum of 4 delays below is the total latency (ms) between 2 points (usually a client and server):
     - ***Propagation delay:*** expressed as a ratio between distance and speed it is the amount of time it takes for a message to travel from sender to receiver.
     - ***Transmission delay:*** The amount of time it takes to push data onto an individual link (network element eg. routers, switches). (Interframe gaps)
     - ***Processing delay:*** The amount of time it takes for data to be processed at some sort of 'checkpoint' 
     - ***Queuing delay:*** Since devices can only process an amount of data at a time, data ends up queuing or buffering. This delay is concerned with the amount of time data sits in a queue waiting to be processed.
     - ***Last-mile latency:*** 'Hops' are longer in the core part of the network with less interruptions in transmission, processing and queuing. There are more frequent, shorter hops towards the end points of a network, thus more delays. Last mile latency is the delay in receiving a signal from an ISP network to a home/office network.
     - ***Round Trip Time (RTT):*** The length of time it takes for a signal to be sent out and responded back to.
     - A data's journey isn't direct from start to end point but rather 'hops' between nodes or routers that process data and forwards it onto the next node on the network.

4. **Explain what bandwidth is and how it works**

   - Bandwidth is a measure of capacity. It's the amount of data that can be transmitted over a network in a specific period of time.
   - Bandwidth isn't fixed and will change over the course of the data's journey. Core network has a larger capacity than the network connected to a home / office.
   - Bandwidth bottleneck is when bandwidth changes from relatively high to low.
   - When dealing with large amounts of data, low bandwidth can be a problem. However latency is usually the cause of network app performance.
   - Increasing bandwidth doesn't necessarily improve the latency

5. **How Does Ethernet Protocol Operate?**

   - Ethernet protocol provides communication between devices on the same local network.

   - Although the physical layer deal with components that are physically connected together, they don't know how to communicate to each other.
   - The protocols of this layer are concerned with identifying physical devices on the network and transporting data between these devices. (eg. computers, switches and routers). Ethernet is the most commonly used protocol. 2 of the most important aspects of Ethernet are framing and addressing.
   - Ethernet frames are a PDU and encapsulates data from the Internet layer above. While the physical network works with streams of bits, Ethernet frames gives bits or binary data structure.
   - An important part of the frame is the source and destination Mac Addresses. Mac Addresses are a form of identity for a device on a local network. Assigned by a manufacturer, It is a set of six, 2 digit hexadecimal numbers that represents a physical or 'burned in' address. It usually doesn't change.
   - The source address of a device is the id of the device that created the frame which will be updated along the data's journey as it reaches different devices. The destination Mac Address is the id of the next intended device that the data is sent to.
   - Frames are directed to intended devices using Switches. Switches consult a MAC address table which contains a list of all the devices connected to it and directs the data off to the recipient accordingly.
   - Although The MAC addressing system works well for local networks it has a problem with scalability. MAC addresses are physical rather than logical. All the digits are flat rather hierarchical, meaning it cannot be broken down into sub divisions. Keeping track of all MAC addresses per local network is virtually impossible task and would result in storing massive tables.

6. **How does Internet Protocol (IP) Operate?**

   - the Internet Protocol enables communication between two networked devices anywhere in the world. its the most widely used protocol used for *inter-network communication*.
   - The purpose of the IP protocol is to establish logical communication between hosts on different networks (as opposed to the same network). It does this by routing data via IP addressing and encapsulating data into this protocols PDU: IP packets. There are 2 versions of IP protocol: IPv4 and IPv6
   - IP addressing - unlike MAC addressing - works logically. Rather than being tied to a device, IP addressing is assigned to devices when they join a network. It is used to to *direct data between one device and another across networks*
   - It's a job of the routers to get the packet to its end point, and they use routing tables, which tell them a certain amount of information about some of the hierarchy to do that. So some routers can get the packet to, say, the province, and then more local routers will take over, and get it to the town etc. Even within these networks the packets can follow different paths depending on things like network congestion and so on.
   - IP addresses must fall within a range of addresses available to a local network. This range is defined by a network hierarchy where the overall network is split into logical subnetworks - each defined by the range of IP addresses available to it. 
   - Eg. if all the addresses in the range between `109.156.106.0` to `109.156.106.255`are assigned to a local network, the address at the start of the range is called the *network address* and the address at the end of the range is called the *broadcast address*. addresses between these addresses can be assigned to any device on the network.
   - network addresses of the range is used to identify a network segment. This means if a router wants to forward an IP packet to any address in the entire range it only needs to keep track of which router on the network controls access to the segment with that network address.  This logic creates a hierarchal structure and also implies that routers don't keep track of every device within an addressable range.
   - all routers lookup a routing table when they receive an IP packet and compares its destination IP address against a list of network addresses. The matching network address determines where the subnet exists in the network hierarchy. This is used to select the best route for the IP packet to travel.
   - IP is intended to provide communication between hosts and direct a message from one host to another host but not beyond that. It's not sufficient enough to be able to transport data from one device's app to another or access the correct service a server provides.

7. **What is a Port number?**

   - **IP Addresses act as id for a device or server, and contains hundreds or thousands of ports, each used for a different communication purpose to that device or server.**

   - IP gets as far as the communication between hosts or devices but not more that that. Different apps are like channels for communication on a host machine. IP addressing only provides a single channel *between* hosts. 
   - Multiplexing is the idea of transmitting multiple signals over a single channel. Demultiplexing is the process in reverse (a single signal transmitted over multiple channels). Multiplexing is implemented through network ports
   - A port is an integer identifier between the range of 0 and 65535 for a specific process running on a host. 
     - 0-1023 are well known ports for commonly used services eg. port 80 is HTTP, FTP is port 20 & 21, SMTP is 25 etc.
     - 1024-49151 are registered ports typically requested by private entities like Micrsoft, IBM and Cisco. Some OS's use ports in this range for client side ephemeral ports.
     - 49152-65535 are dynamic ports or private ports temporarily used by clients and cannot be registered for specific use. They can however be used for customized services.
   - While servers will use the well known ports to provide specific services, the client will use temporary ports. 
   - We use ports to identify specific services running on host machines and implement multiplexing and demultiplexing using source and destination port numbers contained in the TCP/UDP's PDU - segments / datagrams. 
   - segments or datagrams source/destination ports numbers direct app data to specific *processes* on a host. When segments / datagrams are encapsulated into an IP packet, the IP source and destination addresses in the header then direct the data from one *host* to another. 
   - TOGETHER the IP address and port number is what enables end to end communication between specific apps on different machines. The IP port number combo defines a *communication end-point* called a socket eg. 216.3.128.12:8080

8. **What is DNS? How does it work?**

   - This mapping from URL to IP address is handled by the Domain Name System or **DNS**. DNS is a distributed database which translates domain names like `www.google.com` to an IP address, so that the IP address can then be used to make a request to the server. So an address like `www.google.com` might be resolved to an IP address `197.251.230.45`.

     Most people want to use a user-friendly address like `www.google.com`, instead of memorizing a number of digits. DNS databases are stored on computers called **DNS servers**. It is important to know that there is a very large world-wide network of hierarchically organized DNS servers, and no single DNS server contains the complete database. If a DNS server does not contain a requested domain name, the DNS server routes the request to another DNS server up the hierarchy. Eventually, the address will be found in the DNS database on a particular DNS server, and the corresponding IP address will be used to receive the request.

     Your typical interaction with the Internet starts with a web browser when you:

     1. Enter a URL like [http://www.google.com](http://www.google.com/) into your web browser's address bar.
     2. The browser creates an HTTP request, which is packaged up and sent to your device's network interface.
     3. If your device already has a record of the IP address for the domain name in its DNS cache, it will use the cached address. If the IP address isn't cached, a DNS request will be made to the Domain Name System to obtain the IP address for the domain.
     4. The packaged-up HTTP request then goes over the Internet where it is directed to the server with the matching IP address.
     5. The remote server accepts the request and sends a response over the Internet back to your network interface which hands it to your browser.
     6. Finally, the browser displays the response in the form of a web page.

9. **Explain how the client-server model works. What role does HTTP protocol play?**

   - Because the client and the server have an agreement, or protocol, in the form of HTTP, the server can take apart the request, understand its components and send a response back to the client. The client will then process the response strings into content that you can understand. Navigating to websites like Facebook, Google and Twitter means you've been using HTTP all along. 

   - Web browsers are responsible for issuing HTTP requests and processing the HTTP response in a user-friendly manner onto your screen. Web browsers aren't the only clients around, as there are many tools and applications that can also issue HTTP requests.

     The content you're requesting is located on a remote computer called a server. Servers are nothing more than machines or devices capable of handling inbound requests, and their job is to issue a response back. Often, the response they send back contains relevant data as specified in the request.

## TCP & UDP

1. **What is the difference between TCP and UDP?**
   - TCP Transmission Control Protocol
     - connection-oriented protocol
     - reliable data transfer
     - Uses pdu TCP segments for data encapsulation and multiplexing
     - complex and slower (handshake = latency overhead, more complex PDU header)
     - replaces lost, damaged or duplicated data
     - cares about order of data uses sequence numbers
     - prone to queuing delays due to head of line blocking (messages in an order can block subsequent messages in the sequence. If one segment goes missing the rest in sequence can't be processed and are buffered until lost segment is retransmitted)
   - UDP User Datagram Protocol
     - connectionless protocol - doesn't need to establish a connection before it starts sending data 
     - unreliable data transfer / message delivery
     - uses PDU Datagrams
     - simple and faster (no handshake required, simple PDU header, speed, flexibility)
     - Doesn't care about replacing lost, damaged or duplicated data
     - doesn't care about order of data / order of message delivery
     - no flow-control or congestion avoidance mechanisms in place
     - designed to be a protocol built on top of as a base for other services
   
2. **What is the purpose of the TCP handshake and how does it work?**

   - The purpose of a TCP handshake is to establish a reliable connection between app processes. This way app data will not be sent until a connection is properly established between sender and receiver. This affects performance with added round trip latency 

   1. client sends out a `SYN` segment (`SYN` flag set to 1)
   2. server gets `SYN` responds with `SYNACK` segment (`SYN` and `ACK` flag set to 1)
   3. client receives `SYNACK` responds with `ACK` segment (`ACK` flag set to 1)

   - server receives `ACK` connection is now established. Once `ACK` is sent client can immediately start sending app data. Server must wait till `ACK` is received before it can send data back to client. this is to `SYN`chronize sequence numbers used during connection. 
   - Because of its complexity TCP has a real impact on performance but attempts to remedy this with flow control and congestion avoidance.

1. **What is flow control?** 
   - Flow control prevents the sender from giving  the receiver too much data than they can handle and only allows the receiver to process a certain amount of data at a time. 
   - window size field in the TCP header represents how much data the receiver can accept. It is a dynamic number and changes during the connection. 
   - Data waiting to be processed is stored in a buffer. Buffer size depends on allocated memory- (this is based on OS available physical resources).
   - If the buffer is getting full, the window size field can be set to a lower number and the sender reduces the amount of data sent accordingly.
2. **What is congestion avoidance?**
   - When there is more data being transmitted on the network than it can handle. 
   - When this happens excess data is simply 'lost'.
   - Routers can only process so much data at a time and uses a buffer to store data waiting to be processed. If this buffer over-flows excess data is dropped.
   - Lots of lost data = lots of retransmission which affects efficiency. TCP uses data loss to detect network congestion and if lots are occurring TCP assumes congestion and reduces the transmission window size. The algorithm used to determine this varies on which TCP is operating.

## URL's

1. **What are the components of a URL?** 
   eg. http://www.example.com:88/home?item=book

   - `http` is the **scheme**: tells the client how to access the resource (eg. `https`, `ftp`, `mailto`, `git`)
   - `www.example.com` is the **host**: tells the client where the resource is located
   - `:88` is the **port number**: required if you want to use a port other than the default. Unless you specify a different number,  80 is the default port for http requests.
   - `/home/` is the **path** indicates the local resource being requested *(optional).* Sometimes paths can indicate particular resources on the web
   - `?item=book` is a **query string** comprised of query parameters that have the ability to send data to the server. *(optional)*

2. **How do query Strings work?**

   http://www.example.com?search=ruby&results=10

   - `http://www.example.com` is the url

   - `?` is a reserved character that denotes the beginning of a query string
   - `search=ruby` `results=10` are parameter name/value pairs. These are passed to the server from the URL. it asks example.com server to find 10 ruby results. The server uses these parameters based on the application it uses. 
   - `&` is a reserved character used to add /separate more parameters to a query string
   - Query strings are only valid for GET requests.
   - Query strings have a max length and aren't suitable for large amount of data
   - name/value pairs are visible in URL, not suitable for sensitive data
   - special characters like `&` must be encoded

3. **How do you construct a valid URL?**

   - see above

4. **What is URL encoding? When do you use it?**

   - URLs accept only specific characters from the standard 128 ASCII character set
   - Any Reserved/unsafe ASCII characters must be encoded
   - URL encodes non-conforming characters with a % symbol follows by 2 hexadecimal digits representing the ASCII character code
   - Characters must be encoded if:
     - is not found in the ASCII character set.
     - Misinterpreted or modifiable characters. Spaces, percentage, quote marks, hash, less than, greater than, curly and square brackets, and `~` are among some of these characters.
     - Reserved characters that serve a purpose in a URL. `/`, `?`, `:`, `@`, and `&` are all reserved and must be encoded.  `&` is query string delimiter. `:` delimits host/port components and user/password. 
     - Alphanumeric, special characters `$-_.+!'()",` and reserved characters when used for their reserved purposes can only be unencoded in a URL. 

## HTTP Request / Response Cycle

1. **What is the request/reponse cycle?**

   - Entering a url in either a browser or a http tool which is sent to a server that hosts the resource and handles your request. It responds back to your browser with the requested resources.
     - Browsers are designed to automatically parse and display resources in a presentation, user-friendly format
     - HTTP tools are designed to display the raw, unprocessed data from the server
   - HTTP request and response headers give client and server the ability to send additional meta information during the request/response cycle. They are text-based colon-separated name-value pairs
   - Message bodies contains the raw response data

2. **What is a HTTP Request?** 

   - A verb that tells the server what action to perform on a resource

3. **What are the Request components?**

   - Required components are the method and path (request-URI), as they are a part of the start-line/request-line'. The `HOST` header is also required since `HTTP 1.1`
   - Aside from `HOST` all other headers, parameters and message body are optional. 

4. **What is a HTTP Response?**

   - The raw HTTP data sent back by the server after a request has been sent. Every request has a response even if it is an error (except for time outs).

5. **What are the Response components?**

   - Required components are the status code. 
   - Headers and body are optional

6. **What is a `status code`? What are some examples of status code types?**

   - 3 digit number sent back by the server after a request is received (usually from a client) This number indicates the status of the request.

   - `status text` describes the `status code` found under the inspectors status column.

   - | Status Code | Status Text           | Meaning                                                      |
     | :---------- | :-------------------- | :----------------------------------------------------------- |
     | 200         | OK                    | The request was handled successfully. (most common)          |
     | 302         | Found                 | The requested resource has been moved. This Usually results in a redirect to another URL. |
     | 404         | Not Found             | The requested resource cannot be found.                      |
     | 500         | Internal Server Error | The server has encountered a generic error.                  |

7. **Explain what 'state' is and what are some techniques used to simulate state?**

   - HTTP is a stateless protocol and does not hold onto information between request/response cycles. This implies that requests are not aware of each other.
   - However web applications are able to simulate state, that is we are not suddenly logged out of an application like when using Facebook for example. HTTP can maintain a sense of 'statefulness' in the following ways:
     - **Sessions:** *a unique token sent back and forth between client and server to create a sense of constant connection.* This is known as a session identifier or `session id`. Server's work hard to implement session checking, expiration, storing and retrieving session data all to recreate the application's state for the client. 
     - **Cookies:**  *Small files sent from the server to the client that contains session information during the request/response cycle.* Per each request, cookies help identify the current session by comparing the client's cookie with the server's session data. This implies if you visit the same website, it'll recognize the clients session because of the locally stored cookie. If you delete the cookie you'll be automatically logged out of the server
     - **Asynchronous JavaScript and XML (AJAX):** *Allows browsers to send requests and receive responses without fully refreshing the page.* Instead of regenerating every request for a server all client requests are asynchronous (in the background). This means AJAX request's are processed by a `callback` function instead of the standard browser interaction between client and server.

1. **What is the difference between `GET` and `POST` methods? When do we use them?**
   - two most common request methods are `GET` and `POST`. To retrieve data from the server use `GET`. To send data to a server use `POST`
   - GET requests:
     - are used to retrieve a resource, most links are by default `GET` requests.
     - expose parameters in the URL and are not ideal for sensitive data
     - have a max length & aren't suited to large amounts of data
   - POST requests:
     - Are used to send data to a server (eg. usernames and passwords)
     - allow sensitive data to be sent to a server
     - has a much larger capacity for sending information to the server

## Security

1. **What are the security risks that can affect HTTP? What remedies can we use to prevent them from happening?**
   
   - **risks:** 
     - ***packet sniffing:*** hackers reading HTTP client / server request / response messages sent back and forth.
     - ***session hijacking:*** when a hacker gets ahold of a users `session id` they can access their session without knowing their username / password.
     - ***cross site scripting (XSS):*** Allowing users to input HTML / JavaScript directly to be displayed on the site. This can attract hackers to post malicious code, creating potential visitor and server damage. 
   - **remedies:** 
     - ***same-origin policy:*** fundamental to web app security, resources from the same origin can interact with each other without being restricted. This implies that resources from different origins (schemes, ports, hosts) have restricted access to each other.  (links/redirects/form submissions/embedding resources are permitted. Only cross-origin requests are typically restricted. CORS enables this) 
     - ***HTTPS:*** Encrypts every request / response before being transported on the network with TLS: a cryptographic protocol. TLS use certificates as an extra step before interacting with the website.
     - ***reset sessions:*** resetting a session so when the user logs in successfully it creates a new session id thus renders the old one invalid. great for sensitive areas like credit card charging and deleting accounts 
     - ***expiration timers on sessions:*** gives hackers a smaller window to be able to access the application
     - ***sanitize user input:*** prohibit script tags, HTML and JS and use a safer format like Markdown
     - ***escape all user input on display:*** (replace html characters with HTML entities) so the browser doesn't interpret it as code 
   
2. **What are the different services TLS provides?**
   
   - **Encryption:** Encodes a message so it's only read by parties who have been authorized to decode the message.
   - **Authentication:** Verifies the identity of a party in the message exchange
   - **Integrity:** Detects if a message is a fake or has been tampered with
   
3. **How does TLS provide encryption?**

   - **Symmetric Key Encryption:** sender and reciever share a common encryption key. No one else is able to access this key

   -  **Asymmetric Key Encryption:** aka public key encryption uses a 2 keys: 1 public, and 1 private. Both keys are not the same. The public key encrypts and the private key decrypts. only the private key can decrypt the public key and its only available to the message reciever. Public key is openly available. Intended to work in 1 direction. Both keys aren't used in the other direction for security reasons.

   - **TLS Handshake:** securely exchange symmetric keys with asymmetric cryptography. The first key exchange is handled asymetrically and the bulk of the exchange thereafter is symmetrically encrypted. The intitial secure connection setup happens during the TLS handshake. TLS Handshake happens directly after TCP handshake. 

     - Important things to remember!: TLS Handshake:
     - Decides which version of TLS is used to setup secure connection
     - Decides which Algorithm is chosen for the cipher suite
     - Allows Symmetric keys to be exchanged for message encryption.
     - This complexity impacts performance adding upto 2 round trips of latency based on TLS version. This is in addition to the TCP handshake latency. 
     - DTLS Datagram Transport Layer Security is a protocol designed for use with UDP instead of TCP at the Transport Layer.

     > - step 1: `ClientHello` is sent after TCP `ACK` which includes max version of TLS protocol and a list of cipher suites that client can use
     >
     > - step 2: `ServerHello` is sent after recieving `ClientHello` which sets the protocol version and selects cipher suite. It also sends certificate containing its **public key** followed by `ServerHelloDone`  to finish the step.
     > - Step 3: once `ServerHelloDone` key swap process begins which allows both parties to securely get a copy of symmetric encryption key used for bulk of message transfer. The symetric keys generation depends on which key swap algorithm was chosen from the Cipher Suite. 
     > - Step 4: After client has indicated to start using the newly created symmetric keys with `ChangeCipherSpec` and `Finished` Server reponds in kind with `ChangeCipherSpec` and `Finished` Markers. Now both can securely communicate via the symmetric key.

   - **Cipher Suites:** Are a set of cryptographic algorithms used to encrypt, decrypt, and do other related tasks. TLS uses different ciphers to establish and maintain a secure connection. When combined ciphers form a suite which is then sent out to the server by the client based on the ones it supports. Server chooses from them also based on what it supports.
   
4. **Hoes does TLS provide Authentication?**

   - Certificates also act as a form of identity so that the party that provides it is who they say they are. This is not full proof as someone can pose as the owner since certificates are publicly available
   - The way a public key is used to determine authentication varies based on the selected algortihm in the cipher suite. But it ususally follows this process:
     - server sends certificate containing public key
     - server generates a 'digital signature' encrypted by the server's private key.
     - digital signature is transmitted with original data as a message to client
     - client decrypts the signature with server's public key and compares decrypted data to original
     - If the 2 match then the encrypted version could have only been created by a party that has the private key
   - CA's are a trust worthy source that issue a digital certificate to you. They:
     - Verify the party is who they say they and will do so based on the type of certificate being issued to them.
     - Digitally signs the certificate issued to the party. 
   - Root 'CA's are a small group of organizations who dont issue end-user certificates and rely on Intermediate CA's who are authorized by a 'Root CA's to issue certificates on their behalf.  Root CA's can revoke compromised intermediate CA's private keys, invalidating all certificates down the chain. A new certificate would be reissued to them in this case.  
   - Browsers store a list of CA's including their Root certificates (which contains their public key). When a browser checks to see if a certificate is legitimate it can look up the chain to locate the root certificate in its list.
   - The purpose of the chain is the levels of security. The private keys of Root CA's are kept behind intermediate CA's to be as inaccessible as possible.
   - While Root CA's have built a solid reputation on longevity, ultimately the authorization service still relies on trust and isn't 100% reliable.

5. **How does TLS provide Integrity?**

   - TLS is a session layer protocol sitting between application layer (HTTP) and Transport layer (TCP)
   - When transporting app data TLS encapsulates it similar to PDU's - where a data payload is attached to a header and trailer 
   - TLS can also check the data's integerity with the MAC Message Authentication Code. MAC field is similar to checksum fields but it has a different intention.
   - Checksum checks to see if data wasn't corrupted during transport whereas MAC checks to see if the message hasn't been altered / tampered with during transit - adding an extra layer of security. 
   - MAC's are implemented by a hashing algorithm.
     - Sender creates a digest of the data payload that is a bit of data derived from the actual data sent in the message. The digest is created using a hashing algorithm combined with a previously agreed hash value. The hashing algorithm is selected during the TLS handshake and is a part of the cipher suite. 
     - Sender encrypts data payload using symmetric key encapsulates it as a TLS record and passes it to transport layer to be sent to another party.
     - Reciever decrypts data payload using symmetric key and then creates a digest of payload using the same hashing algorithm and hash value. if 2 digests match the integrity of the message is confirmed.