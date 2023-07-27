## Scaled Up and Redundant Web Infrastructure

This web infrastructure represents a scaled-up version of the previously described infrastructure [here](2-secured_and_monitored_web_infrastructure.md). It addresses all Single Points Of Failure (SPOFs) by distributing major components (web server, application server, and database servers) across separate GNU/Linux servers. Additionally, SSL protection is maintained throughout the communication path, and each server's network is secured with individual firewalls. Furthermore, all servers are actively monitored.

## Specifics About This Infrastructure

1. Firewall Between Each Server:
   The implementation of individual firewalls between each server ensures that every server is protected from unwanted and unauthorized access, enhancing the overall security of the infrastructure.

## Issues With This Infrastructure

1. High Maintenance Costs:
   While this scaled-up infrastructure provides enhanced redundancy and fault tolerance, it comes with increased maintenance costs. The distribution of major components to dedicated servers necessitates the purchase of additional hardware, resulting in higher upfront expenses. Moreover, running more servers incurs elevated electricity consumption, contributing to ongoing operational costs. The company would need to allocate funds for purchasing, maintaining, and powering the new servers as well as for managing the existing ones.

It is important to note that despite the higher maintenance costs, the improved redundancy and removal of SPOFs offer greater reliability and better performance, making it a viable trade-off for businesses seeking high availability and stability for their web infrastructure.
