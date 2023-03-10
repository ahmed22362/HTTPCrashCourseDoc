# Anatomy:

- HTTP 1.0 over TCP.
- HTTP 1.1 over TCP
- HTTP 2 over TCP
- HTTP 2 over QUIC (HTTP3)

Internet is built on relation between client and server
The client can be the browser or javascript app or any app that makes HTTP request
The server is a HTTP server like node js or python django etc.
HTTP Request is a message sent by the client to initiate an action on the server
The HTTP request contain items

- URL is the name or the username of the wanted resource on the server
- Method type: Get, Post, Put, Delete it’s indicate what action the cline to made when it initiate the action
- Header: the information the sent with the request
- Body: the data that is sent by the request some methods have body and some don’t like Get don’t have body but Post have.

So when the client sent the message the server response with HTTP response
Like request response contain items:

- Status code: international codes to indicate the status what is the response like the most famous one 404 not found
- Header: contain the information like the request
- Body: if there are shared data will be send in the body

// Built a simple html page and start server with npm package http-server to test this out and
// see the request type and the information( you can see in github)

So how actually http work

Since it built on top of TCP the cline open connection with the server and make a request the server response with the wanted data and then the client close this connection

The problem is most sites have many files and resources to request so for every file or resource you will open and close connection and the TCP is slow and can’t handle large files. all the information the TCP added will take a lot of time.

HTTP 1.0:

- Establish new connection with each request
- Slow
- Buffering

HTTP 1.1:

- Last for 20 years
- Persist the TCP connection:don't close the connection till all the requests are done.
- Law latency: since it’s not waste time in open and close the connections
- Stream with chunk stream: send streams instead of large file

HTTP 2:

- Compression compress the information in the multiplex
- Multiplexing multiple request in one connection
- Push Server
- SPDY
- default by secure is user HTTPS that use encryption connection
- Protocol Negotiation TLS during (NPN/ALPN)

HTTP2 over QUIC (HTTP3):

- Replace TCP with QUIC ( UDP with congestion control)
- All feature of HTTP2
