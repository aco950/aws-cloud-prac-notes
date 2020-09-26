# Pricing and Support

## Steps for Evaluating Your Pricing Needs:
* Examine fundamental characteristics of product
* Estimate usage
* Map usage to prices

## Fundamentals of Pricing
* You pay only for what you need/consume
  * Less dependency on forecasting
* No contracts/termination fees
* Pay less per unit as you grow
* Reserved instances (EC2 and RDS):
  * AURI (all upfront)
  * PURI (partial upfront)
  * NURI (no upfront)
* Storage
  * The more you use, the less you pay.
  * Data transfer in is always free.
* Consolidated Billing 
  * If you have multiple AWS accounts, you can consolidate your AWS
    usage using Consolidated Billing and get tiering benefits based on
    the total usage across your accounts.

## Pricing Details
* Pay for:
  * Compute capacity
  * Storage
  * Outbound data transfer (aggregated)
* No charge for:
  * Inbound data transfer

## Service pricing for AWS offerings
### Amazon EC2
* Charges only for capacity used
* Cost factors
  * Clock-second/hourly billing
    * Resources incur charges only when running
  * Instance configuration
    * Physical capacity of the instance
    * Pricing varies with:
      * AWS region
      * OS
      * Instance type
      * Instance size

* Purchase types
  * On-demand instances
    * Compute capacity by the hour and second
    * Minimum of 60 seconds
  * Reserved instances
    * Low or no upfront payment instances
    * Discount on hourly charge for that instance
  * Spot instances
    * Bid for unused Amazon EC2 capacity
  * Product options
    * Monitoring
      * Use Amazon CloudWatch to monitor instances
      * Basic monitoring (default)
      * Detailed monitoring (fixed reate, prorated partial months)
    * Auto Scaling
      * Automatically adjusts number of instances
      * No additional charge
    * Elastic IP addresses
      * No charge when associated with a running instance
  * OS and software
    * OS prices included in instance prices
    * Sofware:
      * Partnership with other vendors
      * Vendor licenses required
      * Existing licenses accepted through specific vendor 
        programs

### Amazon S3
* What is Amazon S3?
  * Object storage built to store and retrieve any amount of data from 
    anywhere.
  * Provides:
    * Durability, availability, and scalability
    * Comprehensive security and compliance capabilities
    * Query in place
    * Flexible management and data transfer
    * Compatability - supported by partners, vendors, and AWS services
* Things to consider when estimating the cost of Amazon S3:
  * Storage classes
    * Standard Storage
      * 99.999999999% durability
      * 99.99% availability
    * Standard Infrequent Access (S-IA)
      * 99.999999999% durability
      * 99.9% availability
    * Storage cost:
      * Number and size of objects
      * Type of storage
    * Cost factors
      * Pricing based on:
        * Requests
          * Number of requests
          * Type of requests - different rates for GET requests
        * Data transfer
          * Amount of data transferred out of the Amazon S3 region

### Amazon EBS
* Provides block-level storage for your EC2 instances
* Volumes persist independently from the instance
* Analogous to virtual disks in the cloud
* 3 volume types:
  * General Purpose (SSD)
  * Provisioned IOPS (SSD)
  * Magnetic (spinning platters)
* Provides block-level storage for your EC2 instances
* Cost factors:
  * Volumes - all types charged by the amount provisioned per month
  * IOPS:
    * General Purpose (SSD): Included in price.
    * Magnetic: Charged by the number of requests.
    * Provisioned IOPS (SSD): Charged by the amount you provision in 
      IOPS
  * Snapshots (allow data backups for durable recovery) 
    * Added cost per GB/per month of data stored
  * Data transfer
    * Inbound data transfer has no charge
    * Outbound data transfer charges are tiered

### Amazon RDS
* What is Amazon RDS?
  * Relational database in the cloud
  * Cost-efficient and resizable capacity
  * Management of time-consuming and administrative tasks
* Cost Factors
  * Clock-hour billing: Resources incur charges when running.
  * Database characteristics: Engine, size and memory class impacts 
    cost
  * DB purchase type:
    * On-demand database instances are charged by the hour
    * Reserved database instances require upfront payment for database 
      instances reserved
    * Provision multiple DB instances to handle peak loads
  * Provisioned storage
    * No charge for backup storage of up to 100% of database storage
    * Backup storage for terminated DB instances billed at per GB/
      per month
    * Additional storage
      * Backup storage in addition to provisioned storage billed at per 
        GB/per month
    * Deployment type
      * Storage and I/O charges variable
      * Single Availability Zones
      * Multiple Availability Zones
    * Data transfer
      * No charge for inbound data transfer
      * Tiered charges for outbound data transfer

### Amazon CloudFront
* What is Amazon CloudFront?
  * Web service for content delivery
  * Integration with other AWS services
    * Low latency
    * High data transfer speeds
    * No minimum commitments
  * Cost factors
    * Pricing varies across geographic regions
    * Based on:
      * Requests
      * Data transfer out

- AWS Trusted Advisor
  - Provides best practices (or checks) in four categories:
    - Cost optimization
    - Performance
    - Security
    - Fault tolerance 

- AWS Support Plans
  - Support is provided for:
    - Experimenting with AWS
    - Production use of AWS
    - Business critical use of AWS
    - Proactive guidance
      - Technical Account Manager (TAM)
    - Best practices
      - Trusted Advisor
    - Account assistance
      - AWS Support Concierge
  - Support Plans
    - AWS Support offers 4 support plans
      - Basic Support
      - Developer Support
      - Business Support
      - Enterprise Support
 

