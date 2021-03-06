# AWS Core Services

## Amazon Elastic Cloud Compute (EC2)
* Pay as-you-go server resources, also called Amazon EC2 Instances. 
  * Use PuTTYGEN to open .pem file, then save the private key from there 
    in order to access the EC2 instance.

## Amazon Elastic Block Store (EBS)
* Pay as you go (i.e., use).
* Choose between HDD and SSD types.
* Persistent and customizable block storage for EC2 instances.
* Replicated in the same AZ.
* Backup using snapshots.
* Easy and transparent encryption (at no additional cost).
  * Encrypted in transit.
* Elastic volumes.
* Durable and highly-available due to the block-level replication.
* Usage examples:
  * HDD (magnetic) for logs.
  * SSD for the OS.
  * Copy snapshots across different/multiple AZs for disaster recovery.
* Resizing can be done on-the-fly.
* You can switch from HDD to SSD easily.
* Volumes can also be tagged.
  * You can drill down billing per tag, not only with storage, but also 
    with other AWS resources that support tags.

## Amazon Simple Storage Service (S3)
* Fully-managed storage service that provides a simple API for storing
  and retrieving data.
* The data you store in S3 isn't associated with any server and you 
  don't have to manage any infrastructure yourself.
* S3 can hold trillions of objects, of any data file.
  * Data is automatically managed, along with throughput.
* Access anytime or anywhere via low-latency, via HTTP/S.
* Rich security controls.
  * By default, nothing is shared properly.
* Data is held inside a "bucket", tied to a region, which is then 
  replicated across different AZs in that region.
  * https://awsexamplebucket/s3-us-west-2.amazonaws.com/docs/hello.txt
    * Bucket Name: awsexamplebucket
      * Must be globally unique and DNS compliant.
    * Region-specific-endpoint: s3-us-west-2.amazonaws.com
    * Object Key: docs/hello.txt
      * Should be using characters that are safe for URLs.
* Common Use Cases:
  * Storing (common) application data/assets
  * Static web hosting
  * Backup and disaster recovery.
    * You can do cross-region replication.
  * Staging area for Big Data
    * Data stored here can be queried in place and loaded elsewhere and 
      with different tools/services.
  * Via CLI, data can be uploaded, synchronized, etc.

## Amazon Global Infrastructure
* Comprised of:
  * Regions
    * Geographic areas that host 2 or more AZs.
    * The organizing level for AWS services.
    * Pick via latency minimization, costs, and regulatory reqs.
    * Regions are completely separate entities from one another.
      * Not all services are available in all regions.
  * AZs
    * Multiple isolated locations within one geographic area.
    * Collection of data centers in a specific region.
    * Physically and logically isolated from one another, but connected 
      together via a fast, low-latency network.
    * Supplied via different (power) grids from different utilities.
    * Serviced by multiple tier-1 network providers.
    * Protected from failures in other AZs.
      * AWS recommends provisioning your data across multiple AZs as a
        best practice.
  * Edge Locations
    * Host a CDN called Amazon CloudFront.
    * CloudFront is used to deliver content to your customers.
    * Requests are automatically routed to the nearest edge location
      to your customer.
    * Typically located in higly-populated areas.

## Amazon Virtual Private Cloud (VPC)
* The AWS networking service that will meet your networking reqs.
* Allows you to create a private network within the AWS cloud that
    uses many of the same concepts and constructs as an on-premises
    network.
* Allows complete control of network configuration.
  * Ability to isolate and expose resources in the VPC.
* Offers several layers of security controls.
  * Ability to allow and deny specific internet and internal traffic.
* Other AWS services deploy into VPC.
  * Services inherent security built into the network.
* Integrates with numerous AWS services
* Features:
  * Builds on high-availability of AWS regions and AZs.
    * VPCs live within a region ("region-based")
    * Multiple VPCs per account
  * Subnets
    * Divide VPCs
    * Allow VPCs to span multiple AZs
    * Fewer is recommended in order to reduce complexity
  * Route Tables
    * Control traffic going out of the subnets
    * By default, can communicate with one another in the same VPC
    * Can be public or private.
      * For a subnet to be public, we need to attach an IGW (Internet
        Gateway) to the VPC, and update the route table to send non-
        public traffic to the IGW. EC2 instances will also require a
        public IP.
      * An Internet Gateway (IGW) allows access to the Internet from
        Amazon VPC.
  * NAT Gateway
    * Allows private subnet resources to access the Internet.
  * Network Access Control Lists (NACL)
    * Control access to subnets.
    * Stateless.
  * Security Groups
    * One of the highest priorities.
    * Act as built-in firewalls
    * Control access to instances
    * Another method to filter traffic to your instances
    * For example, you can create a rule to allow the entire internet
      0.0.0.0/0, ::/0.

