## Description

This web infrastructure employs a load balancer to distribute traffic between a primary server and a replica server, aiming to reduce the load on the primary server.

## Specifics About This Infrastructure

1. Load Balancer Distribution Algorithm:
   The HAProxy load balancer uses the *Round Robin* distribution algorithm. This algorithm evenly distributes incoming requests among the servers behind the load balancer based on their weights. It ensures fair distribution of processing time, and server weights can be adjusted dynamically.

2. Setup Enabled by the Load Balancer:
   The HAProxy load balancer enables an *Active-Passive* setup, not an *Active-Active* setup. In *Active-Passive*, one server is active (handling requests), while the other is passive (on standby). If the active server becomes unavailable, the passive one takes over. In contrast, *Active-Active* distributes workloads across all nodes to prevent overloading, improving throughput and response times.

3. Database *Primary-Replica* (*Master-Slave*) Cluster:
   The *Primary-Replica* setup designates one server as the *Primary* server, capable of read and write operations. The other server serves as a *Replica* of the *Primary* and handles read-only operations. Data synchronization occurs whenever the *Primary* executes write operations.

4. Difference Between *Primary* and *Replica* Nodes:
   The *Primary* node handles all write operations for the site, while the *Replica* node processes read operations. This allocation reduces read traffic to the *Primary* node.

## Issues With This Infrastructure

1. Multiple Single Points Of Failure (SPOF):
   The Primary MySQL database server, the server containing the load balancer, and the application server connecting to the primary database are all SPOFs. If any of these components fail, the entire site's functionality could be affected.

2. Security Issues:
   Data transmitted over the network is not encrypted with an SSL certificate, making it susceptible to eavesdropping by hackers. Additionally, the absence of a firewall on any server leaves the infrastructure vulnerable to unauthorized access.

3. Lack of Monitoring:
   Without proper monitoring, the status of each server remains unknown. Monitoring is essential for identifying potential issues, ensuring optimal performance, and addressing failures promptly.
