## Well-Architected Framework (5 Pillars)
   - Security
   - Reliability
   - Performance Efficiency
   - Cost Optimization
   - Operational Excellence


## Core Services
   - Elastic Cloud Compute (EC2)
     - Pay as-you-go server resources.

   - Elastic Block Store (EBS)
     - Persistent and customizable block storage for EC2 instances.

   - Simple Storage Service (S3)
     - Object storage service that provides a simple API for data 
       storage and retrieval.


## Global Infrastructure
   - Regions
     - Host 2 or more AZs.
     - Completely separate entities from one another.

   - AZs
     - Multiple isolated locations within a region (geographic area).
     - Collection of data centers within a region.
     - Physical/logical isolation from one another, but connected 
       together via a fast, low-latency network. 
     - Different power grids and tier-1 network providers.

   - Edge Locations
     - Host CloudFront CDNs.
     - CloudFront requests are automatically routed to the customer's
       nearest edge location (as Regional Edge Caches).
     - Typically located in highly-populated areas.


## VPC (Virtual Private Cloud)
  - AWS networking service that allows you to create a private network
    within the AWS cloud.
  - This private (virtual) network closely resembles a traditional 
    network that you would operate in your own data center. 
  - Security Groups act as built-in firewalls for your VPC.
    - You can specify allow rules, but not deny rules.


## High-Availability Tools
   - ELB
   - Elastic IPs
   - Route 53
   - Auto Scaling
   - CloudWatch


## Fault-Tolerant Tools
   - SQS (Simple Queue Service)
   - S3 (Simple Storage Service)
   - RDS (Relational Database Service)


## Integrated Services - Database Products
   - RDS (Relational Database Service)
     - Makes it easy to set up, operator, and scale a relational 
       database in the cloud.
    - You can choose from the following database engines:
      - Amazon Aurora
      - PostgreSQL
      - MySQL
      - MariaDB
      - Oracle
      - MS SQL

   - RedShift
     - Big Data.
     - Fully-managed petabyte-scale data warehouse service in the cloud. 
     - Analytic database with ParAccel technology designed for heavy 
       lifting, crunching big data queries against large datasets.
     - Real-time data analysis.
     - Based on PostgreSQL.

   - DynamoDB
     - Fully-managed proprietary NoSQL database service that supports
       key-value and document data structures.
     - Hadoop integration via Elastic MapReduce.
     - Serverless, no servers to manage.
     - Scalable, across multiple AWS Regions.

   - ElastiCache
     - Offers fully-managed Redis and Memcached for your most demanding
       applications that require sub-millisecond response times.
     - Run and scale popular open-source in-memory data stores in the 
       cloud.
     - Build data-intensive apps or boost the performance of your 
       existing databases by retrieving data from high throughput/low
       latency in-memory data stores.
     - Use cases include real-time services like caching, session 
       stores, gaming, geospatial services, real-time analytics and 
       queuing.

   - DMS (Database Migration Service)
     - Allows you to migrate relational databases, data warehouses,
       NoSQL databases and other types of data stores easily.
     - Use to migrate data into AWS, or between on-premises instances.
     - Migrations can be one-time, or ongoing to sync existing data.


## Integrated Services - Storage Products
   - Snowball
     - Petabyte-scale data transport solution that uses secure 
       appliances to transfer large amounts of data into and out of the 
       AWS cloud.
     - Addresses the issues with large-scale data transfers including
       high network costs, long transfer times and security concerns.
     - Can be used to migrate PB-scale data into S3.

   - S3 (Simple Storage Service)

   - EBS (Elastic Block Store) 

   - EFS (Elastic File System)
     - Scalable, fully-managed elastic NFS file system for use with AWS
       services.
     - 2 classes: standard storage class and infrequent access class.
 
   - Glacier (aka S3 Glacier)
     - Data archiving and long-term backup low-cost storage solution.
     - Secure, durable and flexible.
     - Part of S3.
     - S3 Glacier Deep Archive is for data that is accessed once or 
       twice a year.


## Integrated Services - Other Products
   - Elastic Load Balancing (ELB):
     - Network Load Balancer (NLB)
       - Best suited for TCP/UDP load balancing, where extreme 
         performance is required.
       - Operates at Layer 4 (static IPs, destination ports).
       - Routes traffic to targets within VPC. 
       - NLB cannot assure application availability.

     - Application Load Balancer (ALB)
       - Best suited for load balancing of HTTP/HTTPS traffic and 
         provides advanced request routing that is targeted at the 
         delivery of modern application architectures, including 
         microservices and containers.
       - Operates at Layer 7.
       - Routes traffic to targets within VPC based on the content of 
         the request. 
         - Support for path-based routing (based on the URI in the 
           request).
       - Distributes incoming application traffic across multiple 
         targets, such as EC2 instances in multiple AZs.
       - You can add one or more listeners to your load balancer.

     - Classic Load Balancer (CLB)
       - Deprecated, only for applications built within the EC2-Classic
         network (avoid).
       - Operates at both the request (L7) and connection (L4) level.

   - Auto Scaling
     - Monitors your applications and automatically adjusts capacity in
       order to maintain steady, predictable performance at the lowest
       possible cost (pay only for what you need).

   - Route 53
     - A highly-available and scalable cloud DNS web service.
     - Designed to give users an extremely reliable and cost-effective
       way to route end users to Internet applications.
     - Effectively connects user requests to infrastructure running in 
       AWS and can also be used to route users to infrastructure outside
       of AWS.

   - Lambda
     - Serverless, Function as a Service.
     - Lets you run code without provisioning or managing servers.
     - You pay only for the compute time used.
     - Automatic scaling.

   - Elastic Beanstalk
     - Platform as a service.
     - Easily deploys and scales web applications/services developed 
       with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker.
     - Uses either Apache, NGINX, Passenger, or IIS.

   - SNS (Simple Notification Service)
     - Distributed *pub/sub* system.
     - Fully-managed messaging service for both system-to-system and 
       app-to-person (A2P) communication.
     - Enables you to communicate between systems via pub/sub patterns 
       that enable messaging between decoupled microservice 
       applications, or communicate directly to users via SMS, mobile 
       push and email.
     - You can send alerts based on CloudWatch alarms.

   - SQS (Simple Queue Service)
     - Distributed *queueing* system.
     - Fully-managed queuing service that enables you to decouple and 
       scale microservices, distributed systems, and serverless 
       applications.
     - Eliminates the complexity and overhead associated with managing
       and operating message oriented middleware.
     - You can send, store, and receive messages between software
       components at any volume, without losing messages or requiring 
       other services to be available.

   - SNS vs SQS
     - Entity Type - SNS is a Topic (pub/sub) system, while SQS is a 
       Queue (pub/sub) system.
     - Message consumption - SNS uses a push mechanism (to consumers),
       while SQS uses a pull mechanism (consumers poll and pull).
     - Use case - SNS allows the same message to be processed in many 
       ways (fanout), while SQS allows for the decoupling of 2 
       applications (parralel asyncrhonous processing).
     - Persistence - SNS has no persistence, while SQS allows for 
       messages to be persisted for a certain amount of time.
     - Consumer Type - For SNS, consumers are supposed to be processing
       messages differently, while for SQS all consumers are supposed to
       be identical and process messages in the same exact way.

   - CloudWatch
     - A real-time monitoring and observability service.
     - Provides data and actionable insights to monitor applications,
       respond to system-wide performance changes, optimize resource 
       utilization, and get a unified view of operational health.
     - Set alarms, visualize metrics.

   - CloudTrail
     - Enables governance, compliance, operational auditing, and risk
       auditing of your AWS account.
     - Benefits:
       - Simplified compliance
       - Visibility into user and resource activity.
       - Security analysis and troubleshooting.
       - Security automation.

   - CloudWatch vs CloudTrail:
     - CloudWatch reports on application logs and metrics, while 
       CloudTrail logs provide you specific information on what occured 
       in your AWS account.
     - CloudTrail focuses more on API calls made in your AWS account,
       (who made the request, the services used, the actions performed,
       parameters for the actions, and the response elements returned by
       the AWS service).

   - CloudFront
     - CDN (Content Delivery Network).
     - Securely delivers data, videos, applications and APIs to 
       customers all across the globe, with low latency, high transfer 
       speeds.
     - Allows you to leverage multiple locations around the world to 
       deliver your content, thus allowing your users to interact with 
       your application in a lower latency.

   - CloudFormation
     - Infrastructure as Code.
     - Simplifies the task of repeatedly and predictably creating groups
       of related resources that power your applications.
     - Easy way to model a collection of related AWS and third-party 
       resources, provision them quickly and consistently, and manage 
       them throughout their lifecycles by treating infrastructure as 
       code.
    
   - Web Hosting
     - Provides low-cost ways to deliver websites and web applications.
     - Use cases include a marketing, rich-media or ecommerce website. 
     - Types:
       - Single Page Web App Hosting
       - Simple Static Website Hosting
       - Enterprise Web Hosting
 
   - Kinesis
     - Capture, process, and store video streams for analytics and
       machine learning.

   - EMR
     - Web service that simplifies the processing of large amounts of
       data efficiently.
     - Use Hadoop and other AWS products to do web indexing, data
       data mining, log file analysis, machine learning, scientific
       simulation and data warehousing. 

   - Lightsail
     - Easiest way to launch and manage a virtual private server (VPS).
     - Similar to launching a node on Linode/Digital Ocean.
     - Included is a static IP, DNS management, SSD-backed storage for a
       low, predicatable price ($5 for 750 hours per month).
     - You can scale up and add features as your needs grow.

   - TDM (AWS IoT Things Graph Data Model)
     - Allows users to create abstract representations of IoT devices
       and concepts.
     - Expressed with GraphQL syntax.

   - Trusted Advisor
     - Online tool that provides real-time guidance to help you 
       provision your resources following AWS best practices.
     - Benefits:
       - Cost optimization
       - Improve performance
       - Improve security
       - Increase fault tolerance
       - Check for service limit usage

    - Direct Connect
      - Makes it easy to set up a dedicated network connection from your
        premises to AWS.
      - You can establish private connectivity between AWS and your 
        datacenter, office, or colocation environment over a standard
        Ethernet fiber-optic cable.
      - Reduce network costs, increased throughput, and more consistent
        network experience than Internet-based connections.

   
## Security - Access Control and Management
   - Integration and federation with corporate directories

   - IAM (Identity and Access Management)
     - User - permanent named operator.
     - Group - collection of users.
     - Role - authentication method (nothing to do with permissions).
     - Policy Document - permissions-based JSON document that can be 
       attached to a user, group, or role. Work is done via API.

   - MFA (Multi-Factor Authentication)
     - Adds an extra layer of protection on top of your user name and
       password.
     - Can be enabled for your AWS account and for individual users you
       have created under your account.

   - Cognito
     - "Simple and Secure User Sign-up, Sign-in and Access Control".
     - Lets you add user sign-up, sign-in, and access control to your
       web and mobile apps quickly and easily.
     - Scales to millions of users.
     - Supports sign-in with social identity providers like Google and
       Facebook.

   - SSO (Single Sign-On)
     - Makes it easy to centrally manage access to multiple AWS 
       accounts, business applications and provide users with SSO access 
       to all their assigned accounts.


## Security - Data Encryption
   - KMS (Key Management Service)
     - Secrets management for other AWS services.
     - Can use to protect your own applications that use AWS.

   - CLoudHSM (Hardware-based cryptographic key storage)


## Security - Other
  - Shield 
    - Managed DDoS protection service.
      that safeguards applications running on AWS.
    - 2 tiers of support - Standard and Advanced. Standard is automatic,
      at no additional charge.

   - Inspector
     - Automated *security assessment service* that helps improve the 
       security and compliance of applications deployed on AWS.
     - Automatically checks applications for exposure, vulnerabilities,
       and deviations from best practices.
     - Similar to Nessus Scan product.


## Pricing - Fundamentals
   - You only pay for what you need/consume.
     - You do not pay when things are not running.
   - No contracts/termination fees.
   - Pay less per unit as you grow.
   - Storage 
     - The more you use, the less you pay.
     - Inbound data transfer is always free.
   - Cost drivers:
     - Compute
     - Storage
     - Outbound data transfer


## Pricing - Options and Pricing Models
   - On-demand instances 
     - No long-term commitments or upfront payments
     - Compute capacity by the hour and second

   - Dedicated instances
     - Available with EC2 that is run in a VPC on hardware dedicated to 
       a single consumer

   - Spot instances 
     - Allows you to purchase spare computing capacity at discounted 
       hourly rates.
     - Bid for unused capacity.
     - No upfront commitments.

   - Reserved instances
     - Provide you with the ability to receive a greater discount - up
       to 75% by paying for capacity ahead of time.


## Pricing - Support Plans
   - Basic Support
   - Developer Support
   - Business Support
   - Enterprise Support


## Pricing Calculator
   - Lets you explore AWS services and create an estimate for the cost
     of your use cases on AWS.
   - You can model your solutions before building them, explore the
     price points and calculations behind your estimate, and then find
     the available instance types and contract terms to meet your needs.

