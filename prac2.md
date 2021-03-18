1. What is the internet? How does it work?

   > The internet can be thought a vast network made up of smaller networks that span the globe and are physically connected by cables, wires and various devices.
   >
   > A network at its most basic level is 2 devices setup in a particular way so they can freely communicate and exchange data with each other. For local networks with more than 2 devices they are connected via switches and for connecting 2 or more networks together we use routers. The internet based on a grander scale of this idea.
   >
   > The internet is made up of so many different kinds of devices, models and makes and would not be able to connect and exchange data with one another without the help of protocols. 
   >
   > Protocols are a set of rules that govern how devices exchange data with each other. They address either the same aspect of communication or different aspects of communication.
   >
   > Because the internet is a highly complex structure it can be helpful to think of the internet as a series of layers with protocols working at different layers. Fortunately there are 2 models that can aid us with this: The OSI and the TCP/IP model. These models enable us to zoom in on each layer of the internet and understand how each aspect of the internet works. 
   >
   > Data can also be encapsulated or hidden away from each layer with the help of PDU's (Protocol Data Units.) This allows each layer to provide a service to layer above it.

2. What are the characteristics of the physical network? 

   > The physical network is made up of many physical components which include wires, cables, devices that transmit signals, light and radio waves in order to exchange data with one another. These physical parts of the internet however are bound by physical laws and rules which can be thought of as characteristics of the physical network. These include: Latency and Bandwidth.
   >
   > **Latency** is a measurement of delay and indicates the time it takes for data to move from a start point to an end point then finding the difference between the 2. Latency on the internet is made up of the following: 
   >
   > - Propagation delay: the time it takes for data to travel from sender to receiver (or from one node to another)
   > - Transmission delay: The time it takes for data to pushed onto a 'link'  (the network element between nodes)
   > - Processing delay: the time it takes for data to be processed by a bridging device
   > - Queueing delay: The amount of time it takes data to be waiting in a buffer or a queue for processing by a router or switch.
   >
   > **Bandwidth** on the other hand is a measurement of capacity and indicates how much data is capable of being transmitted in a given time (usually measured in seconds). Bandwidth isn't fixed and varies across the network which means that your effective bandwidth can best be indicated when its at its slowest. When bandwidth moves from relative high to relative low It can bottleneck however when it comes to network app performance, Latency is usually the problem at hand.

3. How do lower level protocols operate?

   > **Ethernet:** Based on the OSI model, sitting atop the physical layer lies the Data Link layer where the Ethernet protocol operates. Ethernet is responsible for connecting devices on the same local network, providing structure and addressing to bits of binary data. This is so they can travel across a network and physically reach its destination. It does this by encapsulating data inside its PDU - Ethernet frames - and addresses each data payload with a Media Access Control or MAC address. MAC addresses are burned in identifiers that enable data within a local network to reach the intended device using a lookup table. 
   >
   > MAC addressing however is not scalable as its too flat and fixed in nature. It only identifies the physical devices themselves on the same network as opposed to where these devices could be located on the internet.
   >
   > **Internet Protocol (IP):** Sitting above the Data link layer of the OSI model lies the Internet layer where the IP protocol functions. This protocol is responsible for providing a hierarchal system for connecting devices from different networks. It does this by encapsulating the data inside its PDU - IP packets and addressing the data with IP addresses. IP addressing is logical in nature as all its digits aren't fixed and represent where a device is located on the internet.

4. What is an IP address? What is a port number?

   > IP addresses are apart of an IP packet header and represent the logical addressing of a source and destination device connected to the internet. The two versions currently in use are IPv4 and IPv6. IPv4 addresses are a set of 4 numbers, 32 bits long and IPv6 has 8 hexadecimal numbers, 128 bits long. IP addresses fall between a range of addresses available to the local network and are split up into logical subnetworks creating a hierarchal structure. 
   >
   > While IP addresses identify devices or hosts on the internet, port numbers allow us to identify and connect to specific processes or applications running on a host. This is made possible thanks to Multiplexing - transmitting multiple signals over a single channel and Demultiplexing, which works in reverse.
   >
   > Together IP addresses and port numbers when combined form a communication end point called a socket. Sockets establish connections between 2 processes on 2 different devices on 2 different networks.

5. How does DNS work?

   >IP addresses are often difficult to remember so more user-friendly addresses called URL's like `www.google.com` are mapped to IP addresses. Domain name system or DNS servers are a very large hierarchal network of distributed databases devoted to translating URL's into an IP addresses.  When we enter a URL into a web browser for the first time the browser or client creates a DNS request to the DNS servers who will locate the IP address for you by routing the request up the hierarchy until the IP address is found. The IP address is then used to receive the client's request.
   >
   >( We use DNS to look up what is typed into a browser, to find a specific domain. DNS uses the domain in the URL typed into the browser to look up the IP address associated with that domain. The IP address is then used to look up the requested resource.)

6. How does the client-server model work? What role does the HTTP protocol play within that model?

   > From an application stand point, HTTP is an underlying protocol / agreement that allows clients and servers to communicate with one another through the exchange of text-based messages. HTTP enables client's to make a **request** to a server and waits for a **response**. Servers examine clients' HTTP requests and send back a response. Clients will then process the servers response into content that we can understand. An example of this is requesting https://www.google.com and receiving the google homepage. 
   >
   > ( that serve as a link between applications and the transfer of [hypertext](http://en.wikipedia.org/wiki/Hypertext) documents)

7. How does the TCP and UDP protocols work and what are their similarities and differences?

   >TCP (Transmission Control Protocol) and UDP (User datagram protocol) are protocols that enable the transmission of data from one app process on the internet to another. While they both support multiplexing, error detection and operate at the transport layer of the OSI and TCP/IP model, they share many differences. For instance TCP is connection orientated protocol and works with PDU segments that has a more complex header.  It's also slower than UDP, yet it has a more reliable way to transfer data thanks to its 3 way handshake and sequencing numbers. 
   >
   >UDP on the other hand is a connectionless protocol and works with Datagrams as its PDU, which have a simpler header. UDP requires no handshake which increases its speed and flexibility. however because of this it lacks the reliability that TCP has and works as sort of a base template for other services to be added to it.
   >
   >(UDP does provide error detection via a checksum, though this is optional if using IPv4.)

8. What is the purpose of the 3 way handshake and how does it work?

   >The purpose of a TCP 3 way handshake is to establish a TCP connection between two different applications. This way app data will not be sent unless a proper connection is established between sender and receiver.  
   >
   >If the initial sender is a client it will first send out an `SYN` segment to the recipient, in this case a server. Upon receiving `SYN` server will then send out a `SYNACK` segment to the client. Once the client receives the `SYNACK` and sends back a final `ACK` segment it can straight away begin sending app data to the server. The server can only send app data back to the client once it receives the `ACK` segment.

9. What is Flow Control and Congestion Avoidance?

   > TCP handshake affects performance, adding an additional RTT to the overall latency. To combat this TCP employs flow control and congestion avoidance. 
   >
   > Flow Control prevents a device from receiving more data than it can handle, and only allows a certain amount of data to be processed at a time. This is controlled by the window size field in the TCP header which indicates how much data can be received at a given time. Data waiting to be processed is stored in a buffer, which if getting too full the window size will be reduced. 
   >
   > (Flow Control is a mechanism to prevent the sender overwhelming the receiver with more data than it can process. Each participant in a connection lets the other participant know how much data it is willing to accept using a field in the TCP header.)
   >
   > Congestion avoidance attempts to stop excess data from being 'dropped' when there is more data on the network than it can handle. Lots of lost data can lead to too much retransmission which affects overall performance. In this case the window size is reduced so less retransmission occurs.
   >
   > (Congestion avoidance is a process by which TCP uses data loss (based on the volume of retransmissions required) as a feedback mechanism to determine how congested the network is, and adjusts the amount of data being sent accordingly.)

10. What are the components of a URL?

    > **The Scheme** `http`: comes before the colon and 2 forward slashes. This tells the client how to access the resource. (The scheme identifies which protocol should be used.)
    >
    > **The Host** `www.example.com`: tells the client where the resource is hosted or located
    >
    > **The Port** `:88`: Only required if you are using another port number other than the default `:80` 
    >
    > **The Path** `/home/`: indicates which **local** resource is requested (optional)
    >
    > **The Query string** `?item=book` made up of query parameters (optional)
    >
    > (we use path and query to pass information from the URL to the application server)

11. How do you construct a valid URL?

    >In addition to the above query strings:
    >`?` is reserved to indicate the start of a query string
    >
    >`search=ruby` is a parameter name/value pair. They are sent from a URL to a server. It's asking `example.com` to find 10 ruby results.
    >
    >`&` reserved for adding or separating parameters in a query string

12. What is URL encoding and when is it used?

    >When it comes to URL's, only certain characters can be accepted from the standard ASCII character set. reserved characters such as `&` and `?` who aid in the construction of a URL and generally any other non-alphanumeric characters (`$-_.+!'()"`) must be encoded.
    >
    >Encoded characters are indicated with a `%` and 2 hexadecimal digits representing ASCII code of the character (eg.` " "` is encoded as `%20` it can also be encoded as `+`)

13. Explain what HTTP requests and responses are. What are their components?

    >**HTTP Requests:** **is made up of a request line, headers, and an optional body.** 
    >
    >Essentially a request is when you enter a URL address in a browser or client. A server will handle your request and send back a response to your browser which will process and display the rendered result.
    >
    >Required components of a request are the **method** (GET), the **path** (request-URI),  and the **HTTP version** used `HTTP 1.1` (if it's HTTP 1.0 or greater) as they all form the **request-line**. If HTTP 1.1 is being used then the **host** is also a required component. All other headers, parameters and body are optional.
    >
    >```
    >Request Line: GET /utilities/weatherfull HTTP/1.1
    >Host address: restapi.demoqa.com
    >```
    >
    >**HTTP Responses: is made up of a status line with optional headers, and an optional body**
    >
    >This is the raw HTTP data that's sent from the server as per the clients request. Ever request has a response, even if its an error (timeouts are the exception.)
    >
    >Required components are the **status code** and **status text**. All headers and body is optional
    >
    >```
    >Status Line: HTTP/1.1 200 OK
    >```

    

14. Describe the HTTP request / response cycle

    >The HTTP request/response cycle typically takes place between a client and a server. Upon entering the the URL of a webpage in a browser's address bar a text-based HTTP (`GET`) request is made. Assuming the webpage isn't cached A DNS request is made to DNS servers to lookup and obtain the IP address of the domain. Upon receiving the IP address the client will then send the HTTP request to the server. The server will then process the request and send a response back to the client (`200 OK`) - displaying the webpage.  
    >
    >(If your device already has a record of the IP address for the domain name in its DNS cache, it will use this cached address)

15. What are status codes? Describe some examples of different status code types

    >Status codes are a required part of a HTTP response. They're comprised of a 3 digit number followed by status text describing the outcome of the request
    >
    >- `200` - OK: the request was handled successfully
    >- `302` - Found: Usually this indicates that the resource has been moved and will automatically redirect you to the new location
    >- `404` - Not Found: The requested resource isn't found
    >- `505` - Internal Server Error: Generic server side error

16. What is meant by state in the context of the web? What are some techniques used to simulate state?

    >'State' refers to the information that a server holds onto. HTTP however, is designed to be a 'stateless' protocol meaning that each request / response cycle is independent and unaware of the ones that came before and after it. While this is great for cleanup purposes and resilience, it can make it difficult for web developers to create a sense of state for web applications such as Facebook.
    >
    >Fortunately there approaches that help simulate state: Sessions, Cookies and AJAX. Session ids are unique tokens appended to requests and are passed back and forth between client and server. This is done between requests to create a feeling of of persistent connection and aids in identifying the client.
    >
    >During the request/response cycle cookies also help simulate state. They are temporary pieces of information sent from the server and stored on the client for the purposes of identifying the current session data located on the server.
    >
    >AJAX (Asynchronous Java Script and XML) main goal is to allow clients to send requests and process responses without completely refreshing the whole page. By allowing only certain elements of an application to be updated without reloading everything greatly reduces overhead associated with HTTP. Ajax is just like normal HTTP request except its first processed by a `callback` rather than the plain browser.
    >
    >

17. What is the difference between `GET` and `POST`? When do we use each?

    >`GET` and `POST` are common HTTP request methods clients use during the request response cycle. `GET` is used when we want to retrieve data from a server such as the webpage `https//:www.google.com` , whereas `POST` is use when we want to send and update data stored on the server such as supplying login information to Github. 
    >
    >While most links are by default `GET` requests, `GET` requests for the most part are unable to change values on a server.  While it can send parameters via the URL, they are fully exposed making it unsuitable for more sensitive data. They also have a max length and do not have the capacity for large amounts of data.
    >
    >`POST` requests on the other hand make use of the request's body. This allows for a much larger data capacity to be sent to the server as well as hiding more sensitive information, such as login information.

18. What are some of the security risks that affects HTTP? What are some measures we can take to mitigate against these risks?

    >Since HTTP requestts and responses consist of text-base messages, they are inherently insecure and open to packet sniffing. This technique allows hackers to read messages which contains the session id. If gotten ahold of it can be used to pose as a user and login to their session without knowing their username / password. This is known as session hijacking. 
    >
    >To counter this we can **reset the session** by rendering an old session as invalid and now useless to the hacker, and create a new session id, prompting the user again for authentication. Similarly we can also **set an expiration time** on a session, giving a hacker even less time to pose as a user. Using **HTTPS** throughout the entire app works well as it just encrypts all requests and responses, rendering the information unreadble during transmission.
    >
    >Another important aid for session hijacking is the **Same-origin policy**, where an origin refers to the same scheme, hostname and port. Same-origin policy restricts specific interactions between resources from different origins but allows unrestricted interactions between resources from the same origin. It targets cross origin requests that are programatically accessible by API's. However when web developers legitmately need unrestricted access to cross origin requests they use CORS to handle this issue.
    >
    >Cross Site Scripting (XSS) is also another attack than can happen when you allow HTML or JS input that can be displayed on a site. Without proper input sanitization attackers can post malicious code which can damage both the server and potential visitors.
    >
    >To remedy this developers must **sanitize user input** by removing problematic input like script tags or better still, forbid HTML or JS  altogether. Opt for a more safer format like Markdown. We can also **escape all user input** when it's displayed so the browser won't interpret it as code.

19. What are the services TLS provides? Briefly explain how each of these services work.

    >Operating between HTTP and TCP protocols the TLS (Transport Layer Security) Protocol designed to add security to the message exchange process over an unsecure channel. It does this by providing Encryption, Authentication and Integrity services. 
    >
    >The Encryption service encodes HTTP messages so it can only be read by those that have the authority to decode the message. It does this using the TLS handshake which takes place directly after the TCP handshake. TLS handshake agrees on the TLS version and a set of cryptographic algorithms that will form a cipher suite used for data encryption/decryption etc. Symmetrical keys are relied on for the bulk of secure message transfer but they must first be exchanged using Asymetrical Encryption. Asymmetrical encryption is designed to flow in a one way direction using 2 keys: public and private, for encryption and decryption respectively. While TLS Handshake allows for a very secure message transfer it results in several round trips of latency, reducing overall performance.
    >
    >(The *TLS Handshake* must be performed before secure data exchange can begin)
    >
    >The Authentication service verifies a party's identity during the message exchange process. This is done using publicily available digital certificates, which are exchanged during the TLS handshake process but also proves the owner's identity. Certificates are issued and signed by a certificate Authority or (CA) once they verifiy that the owner is are who they say they are. There are different levels of CA's, with intermediate CA's issuing certificates to end-users on behalf of highly trusted Root CA's - which are small groups of organizations approved by OS vendors. Each CA will issue a certificate validating the certificate of the CA below them, creating a certificate heirarchy and a chain of trust. This heirarchy is available for anyone to view but ultimately relies on trust. 
    >
    >(CAs digitally sign the certificates they issue, generating a signature using their own private key. Certificates are generally signed by one CA. An Intermediate CA will sign an end-user's certificate, and a Root CA will sign the Intermediate CA's certificate. This creates the 'chain' in the chain of trust.)
    >
    >The Integrity service checks to if a message is a fake or has been tampered with during message transfer. This is done using a Message Authentication Code (MAC) available as a header field in a TLS's PDU - a record. The MAC's job is to check to see if a message hasn't been tampered with during transit. It's is an algorithmically generated code included in TLS record as a way of checking the integrity of the record payload.
    >
    >(MAC is implemented using a hashing algortithm and a pre agreed hash value which is used to extract a small amount of data from the original data, creating a digest. The sender encrypts this data payload and encapsulates it in TLS record. Upon recieving the Data payload and dycrypting it using their symmetric key, reciver will also create a digest using the same algorithm and hash value. If sender and reciever's digest's match it the integrity of the message is confirmed. )

    

