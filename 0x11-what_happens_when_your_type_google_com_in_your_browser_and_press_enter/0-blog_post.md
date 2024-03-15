# What Happens?
`What happens when you type https://www.google.com in your browser and press Enter.`

To answer this question, I will proceed to break down the URL; `https://www.google.com`.
- `https://` is a scheme, it is a Secure Hypertext Transfer Protocol.
- `www` is a subdomain to `google.com` domain, it works like an identifier or an address to the website that points to a specific server IP address serving the website.

## Browser query for domains IP address
When a user types in the URL and presses enter, the browser first needs to figure out the IP address of the server hosting the website. It does this by performing a DNS query (also known as DNS request) where the user's computer (DNS client) asks for the IP address associated with the domain name from a DNS server (a computer server that contains a database of public IP addresses and their associated hostnames.)

## The TCP/IP Connection
Once the DNS client attains the IP for the domain it proceeds to initiate a connection to it using a process called TCP 3-way handshake (where both the client and the server synchronize a.k.a SYN and acknowledge a.k.a ACK each other). Where the client chooses an initial sequence number, set in the first SYN packet. The server also chooses its own initial sequence number increments the client's SYN number sets it the SYN/ACK packet and waits for the client to ACK by incrementing its SYN number.

## HTTPS/SSL
TCP/IP connection has been done, the browser proceeds to communicate with the server using a secure protocol, HyperText Transfer Protocol Secure (HTTPS). This protocol defines different types of requests (eg; GET, POST and PUT) and responses that are secured by a standard security protocol called Secure Sockets Layer (SSL) which encrypts and decrypts the data from the client to the server infrastructure at the load balancer.

## Load Balancer
Once a connection has been established, the user's browser (client) and google’s website (server) are able to send/receive data between each other over HTTPS protocol. In a situation where there are so many users (requests) visiting the website, the load balancer distributes those requests across a number of servers to prevent downtimes and a Single Point of Failure (SPOF).

## The Great Wall
The great wall is also known as the firewall. It is designed to carefully analyze incoming traffic based on pre-established rules and filter traffic coming from unsecured or suspicious sources to prevent attacks. The request from the users is analyzed by the firewall and if it isn’t malicious or suspicious it is allowed to connect to a webserver that is going to be assigned by the load balancer.

## Web and Application Server
Let’s recap, the user types the URL from the browser and types enter, then the browser figures out the IP address of the domain name by performing a DNS lookup. Once the IP is found the browser initiates a TCP/IP connection, then the request is analyzed by the firewall, and then gets to the load balancer that distributes it to a web server. A web server is software and hardware that only handles HTTP/HTTPS  requests and servers static content like simple HTML pages, plain text files, or images.

An Application server runs behind a web server and in front of a Database Management System (DBMS). Its main purpose is to generate dynamic content supporting an application’s development and delivery providing business logic behind the application.

## Data Management
Above we mentioned the Database Management System (DBMS); it is a program that allows the interaction with a database (*an organized collection of structured information, or data stored in a computer system*) to define, manipulate, retrieve and manage the data according to the request. The Database in this context will serve the user any information he is querying from google.com and store any information like account creation.

Once the request has been processed the webserver responds back to the user/client and that’s what happens when you type `https://www.google.com` in your browser and press `Enter`.

## Everything's better with a pretty diagram
![alt text][logo]

[logo]: https://file.notion.so/f/f/a5d58d30-fa97-48f8-b839-144447a01db7/d2ece046-04f3-4d00-92c6-7438be86e94c/whathappens.gif?id=6c4663b7-f4d8-42cc-b2c4-37aeed3cb49b&table=block&spaceId=a5d58d30-fa97-48f8-b839-144447a01db7&expirationTimestamp=1710554400000&signature=yW79ZdJAr6EA4Khi9sOai-Fky9yliThsi_ENn6wKXjU "Everything's better with a pretty diagram"
