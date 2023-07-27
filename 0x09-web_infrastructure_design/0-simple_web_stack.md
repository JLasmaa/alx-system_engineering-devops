## Description

This is a basic web infrastructure hosting a website accessible via `www.foobar.com`. The server lacks firewalls or SSL certificates for network protection, and all components (database, application server) share the server's CPU, RAM, and SSD resources.

## Specifics About This Infrastructure

1. What a server is:
   A server is a computer hardware or software that provides services to other computers, typically known as *clients*.

2. The role of the domain name:
   The domain name serves as a user-friendly alias for an IP Address. For instance, `www.wikipedia.org` is easier to remember than `91.198.174.192`. The IP address and domain name alias are mapped in the Domain Name System (DNS).

3. The type of DNS record `www` is in `www.foobar.com`:
   `www.foobar.com` uses an **A record**, which can be verified by running `dig www.foobar.com`. It associates a hostname with its corresponding IPv4 address. 

4. The role of the web server:
   The web server is software/hardware that handles requests via HTTP or secure HTTP (HTTPS) and responds with the requested content or an error message.

5. The role of the application server:
   The application server installs, operates, and hosts applications and services for end users, IT services, and organizations. It facilitates hosting and delivering high-end consumer or business applications.

6. The role of the database:
   The database maintains an organized collection of information that can be easily accessed, managed, and updated.

7. What the server uses to communicate with the client (computer of the user requesting the website):
   Communication between the server and the client occurs over the internet network using the TCP/IP protocol suite.

## Issues With This Infrastructure

1. There are multiple Single Points Of Failure (SPOF) in this infrastructure:
   For example, if the MySQL database server experiences downtime, the entire website would be inaccessible.

2. Downtime when maintenance is needed:
   Maintenance checks on any component require either putting them down or turning off the server. As there is only one server, the website experiences downtime during maintenance.

3. Limited scalability with high incoming traffic:
   Scaling this infrastructure is challenging because all required components reside on a single server. As a result, the server may quickly run out of resources or slow down when faced with a high volume of requests.
