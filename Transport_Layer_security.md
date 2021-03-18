## What to Focus On

> HTTP on its own doesn't provide any means of secure message transfer. Using TLS adds a level of security that HTTP lacks. TLS is a complex topic and could take up a whole course on its own! Use the following guidelines to focus your studies.

#### Understand that TLS provides for secure message exchange over an unsecure channel

> In learning about TLS, start from the basis of what unsecure HTTP message transfer looks like. Build on your understanding of HTTP from previous lessons in order to clearly understand what TLS adds to the mix.

#### Learn that there are multiple aspects to security

> TLS provides a number of different services. Learn what each of these services provide, and the particular problems each of them aims to address.

## Summary

### Transport Layer Security (TLS) Protocol

- *HTTP Requests and Responses* are transferred in *plain text*; as such they are *essentially insecure*.
- We can use the *Transport Layer Security* (TLS) Protocol to add security to HTTP communications.

### TLS Encryption

- *TLS encryption* allows us to *encode messages* so that they can only be read by those with an authorized means of decoding the message

- TLS encryption uses a combination of *Symmetric Key Encryption* and *Asymmetric Key Encryption*. Encryption of the initial key exchange is performed asymmetrically, and subsequent communications are symmetrically encrypted.

- The *TLS Handshake* is the process by which a client and a server *exchange encryption keys*.
- The *TLS Handshake* must be performed before secure data exchange can begin; it involves *several round-trips of latency* and therefore has an *impact on performance*.
- A *cipher suite* is the *agreed set of algorithms* used by the client and server during the secure message exchange.

### TLS Authentication

- *TLS authentication* is a means of *verifying the identity* of a participant in a message exchange.
- TLS Authentication is implemented through the use of *Digital Certificates*.
- Certificates are *signed* by a *Certificate Authority*, and work on the basis of a *Chain of Trust* which leads to one of a small group of highly trusted *Root CAs*.
- Certificates are *exchanged* during the *TLS Handshake* process.

### TLS Integrity

- *TLS Integrity* provides a means of *checking* whether a message has been *altered or interfered with* in transit.
- TLS Integrity is implemented through the use of a *Message Authentication Code* (MAC).