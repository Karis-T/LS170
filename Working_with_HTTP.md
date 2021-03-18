## What to focus on

#### Focus on HTTP

> Although we're using bash and various network utilities in this lesson, those things aren't the primary focus here and we don't expect you to master them; we're simply using them to demonstrate how HTTP functions at a more practical level and to reinforce the concepts covered in the previous lesson. The focus of this lesson is still very much HTTP, and how it enables network communication between a client and a server.

#### HTTP is concerned with the structure of messages

> At its core, HTTP is a set of rules concerned with the syntax and structure of messages exchanged between applications. Working with HTTP is ultimately about understanding what those rules mean, and knowing how and when to apply them.

#### HTTP is a Request-Response protocol

> One of the fundamental aspects of HTTP is its Request-Response behavior. As you work through the lesson keep a focus on this behavior, and try to form a solid mental model around it.

## Summary

- HTTP is a *text-based* protocol. HTTP Request and Responses involve sending text between the client and server
- In order for the protocol to work, the Request and Response must be structured in such a way that both the client and the server can understand them.
- With HTTP/1.1, the end of the headers is indicated by an *empty line*.
- The `Content-Length` header can be used to indicate the *size of the body*. This can help determine where the HTTP message should end.