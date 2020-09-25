# Fault Tolerance and High Availabilty

## Fault Tolerance:
* The ability for a system to remain operational even if some of the
  components of that system fail.
* Built-in redundancy of an application's components.

## High Availability (ensures that):
* Systems are always functioning and available
* Downtime is minimized
* Minimal human intervention is required
* Minimal up-front financial investment

## High Availability - On Premises vs AWS:
* Traditional (on premises)
  * Very expensive
  * Only mission-critical applications
* AWS
  * Multiple servers
  * Multiple Availability Zones
  * Multiple Regions
  * Access to fault-tolerant services to use as you please

## High Availability Service Tools
#### Elastic load balancers
* Distributes incoming traffic (loads)
* Sends metrics to Amazon CloudWatch
* Triggers/notifies
  * High latency
  * Over utilization
#### Elastic IP addresses
* Are static IP addresses
* Mask failures (if they were to occur)
* You can continue to access applications even if an instance fails
#### Amazon Route 53
* Authoritative DNS service
  * Translates domain names to IP addresses
* Supports:
  * Simple routing
  * Latency-based routing
  * Health checks
  * DNS failovers
  * Geo-location routing
#### Auto Scaling
* Terminates and launches instances based on specified conditions
* Assists with adjusting or modifying capacity
* Creates new resources on demand
#### Amazon CloudWatch
* Distributed statistics gathering system
* Tracks your metrics of your infrastructure
* Create and use your own custom metrics
* Used with auto scaling

## Fault Tolerant Tools
* Amazon Simple Queue Service (SQS)
* Amazon Simple Storage Service (S3)
* Amazon Relational Database Service (RDS)

