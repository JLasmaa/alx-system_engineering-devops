# Secured and Monitored Web Infrastructure

![Image of a secured and monitored infrastructure](2-secured_and_monitored_web_infrastructure.PNG)

## Description

This web infrastructure consists of three servers and is designed to be secured, monitored, and capable of serving encrypted traffic.

## Specifics About This Infrastructure

1. Purpose of the Firewalls:
   The firewalls play a crucial role in safeguarding the web servers from unwanted and unauthorized users. They act as intermediaries between the internal network and the external network, effectively blocking incoming traffic that matches criteria associated with potential threats.

2. Purpose of the SSL Certificate:
   The SSL certificate is utilized to encrypt the traffic exchanged between the web servers and the external network. By encrypting the data, it mitigates the risk of man-in-the-middle attacks (MITM) and prevents network sniffers from intercepting sensitive information. The SSL certificate ensures data privacy, integrity, and enables secure identification.

3. Purpose of the Monitoring Clients:
   The monitoring clients are responsible for overseeing the servers and external network. They continuously analyze the servers' performance and operations, providing valuable insights into their overall health. If any server is not performing as expected, the monitoring tool alerts administrators. The monitoring clients conduct tests to assess server accessibility, measure response times, and promptly notify administrators of issues, including corrupt or missing files, security vulnerabilities, and other potential problems.

## Issues With This Infrastructure

1. SSL Termination at Load Balancer Level:
   Terminating SSL at the load balancer leaves the traffic between the load balancer and the web servers unencrypted. This introduces a potential security vulnerability, and it is important to ensure that SSL encryption is maintained throughout the entire communication path.

2. Single MySQL Server Scalability:
   Relying on a single MySQL server raises concerns about scalability. As the web infrastructure grows and traffic increases, a single MySQL server may become a performance bottleneck and a single point of failure. Considering a more scalable database solution, such as database replication or sharding, would be beneficial.

3. Identical Components on Servers:
   Equipping servers with the same components may lead to resource contention, such as CPU, memory, and I/O. This can result in suboptimal performance and make it challenging to pinpoint the source of issues. An approach that allows for better resource allocation and scalability, such as distributing specialized roles across servers, is worth considering to enhance performance and manage growth effectively.
