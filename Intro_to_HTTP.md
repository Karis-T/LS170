## What to Focus On

#### Develop a clear understanding of the role of HTTP

> The focus of this lesson is on HTTP, however it doesn't function in isolation. As you work through the lesson, try and build a picture of the functioning of the web as a combination of multiple different technologies, a combination within which HTTP has a specific role.

#### Break things down into individual components

> Ensure clarity within your mental models by breaking concepts like HTTP and URLs into specific components, and understanding the purpose of each of those components.

## Summary

### DNS

- The ***Domain Name System*** (DNS) is a distributed database which *translates a domain name* such as `google.com` *to an IP Address* such as `216.58.213.14`.

### URI & URL

- A ***URI*** is an *identifier* for a *particular* resource within an information space.
- A **URL** is a subset of URI, but the two terms are often used interchangeably.
- URL components include the *scheme*, *host* (or hostname), *port*, *path*, and *query string*.
- ***Query strings*** are used to *pass additional data* to the server during an HTTP Request. They take the form of *name/value pairs* separated by an `=` sign. Multiple name/value pairs are separated by an `&` sign. The start of the query string is indicated by a `?`.
- *URL encoding* is a technique whereby *certain characters* in a URL are *replaced with an ASCII code*.
- URL encoding is used if a character has no corresponding character in the ASCII set, is unsafe because it is used for encoding other characters, or is reserved for special use within the url.

### HTTP

- A single HTTP message exchange consists of a *Request* and a *Response*. The exchange generally takes place between a *Client* and a *Server*. The client sends a Request to the server and the server sends back a Response.
- An ***HTTP Request*** consists of a *request line*, *headers*, and an optional *body*.
- An ***HTTP Response*** consists of a *status line*, optional *headers*, and an optional *body*.
- ***Status codes*** are part of the status line in a Response. They indicate the status of the request. There are various categories of status code.
- **HTTP** is a *stateless* protocol. This means that each Request/ Response cycle is independent of Request and Responses that came before or those that come after.
- *Statefulness can be simulated* through techniques which use *session IDs*, *cookies*, and *AJAX*.
- HTTP is *inherently insecure*. Security can be increased by using *HTTPS*, enforcing *Same-origin policy*, and using techniques to prevent *Session Hijacking* and *Cross-site Scripting*.