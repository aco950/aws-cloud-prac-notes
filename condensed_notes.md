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
    - Object storage service that provides a simple API for data storage
      and retrieval.


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


- VPC (Virtual Private Cloud)
  - AWS networking service that allows you to create a private network
    within the AWS cloud.
  - This private (virtual) network closely resembles a traditional 
    network that you would operate in your own data center. 
  - Security Groups act as built-in firewalls for your VPC.
    - You can specify allow rules, but not deny rules.


- High-Availability Tools
  - ELB
  - Elastic IPs
  - Route 53
  - Auto Scaling
  - CloudWatch


- Fault-Tolerant Tools
  - SQS (Simple Queue Service)
  - S3 (Simple Storage Service)
  - RDS (Relational Database Service)


- Integrated Services - Database Products
  - RDS (Relational Database Service)
    - Makes it easy to set up, operator, and scale a relational database
      in the cloud.
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
    - Use cases include real-time services like caching, session stores,
      gaming, geospatial services, real-time analytics and queuing.

  - DMS (Database Migration Service)
    - Allows you to migrate relational databases, data warehouses,
      NoSQL databases and other types of data stores easily.
    - Use to migrate data into AWS, or between on-premises instances.
    - Migrations can be one-time, or ongoing to sync existing data.

- Integrated Services - Storage Products
  - Snowball
    - Petabyte-scale data transport solution that uses secure appliances
      to transfer large amounts of data into and out of the AWS cloud.
    - Addresses the issues with large-scale data transfers including
      high network costs, long transfer times and security concerns.
    - Can be used to migrate PB-scale data into S3.
  - S3 (Simple Storage Service)
  - EBS (Elastic Block Store) 
  - EFS (Elastic File System)
    - Scalable, fully-managed elastic NFS file system for use with AWS
      services.
    - 2 classes: standard storage class and infrequent access class.

- Integrated Services - Other Products
  - Application Load Balancer (part of ELB - Elastic Load Balancer)
    - Serves as the single point of contact for clients. 
    - Distributes incoming application traffic across multiple targets,
      such as EC2 instances in multiple AZs.
    - You can add one or more listeners to your load balancer.
    - Support for path-based routing (based on the URI in the request).

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
    - Easily deploys and scales web applications/services developed with
      Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker.
    - Uses either Apache, NGINX, Passenger, or IIS.

  - SNS (Simple Notification Service)
    - Distributed *pub/sub* system.
    - Fully-managed messaging service for both system-to-system and 
      app-to-person (A2P) communication.
    - Enables you to communicate between systems via pub/sub patterns 
      that enable messaging between decoupled microservice applications,
      or communicate directly to users via SMS, mobile push and email.
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
    - Entity Type - SNS is a Topic (pub/sub) system, while SQS is a Queue
      (pub/sub) system.
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

  - CloudFront
    - CDN (Content Delivery Network).
    - Securely delivers data, videos, applications and APIs to customers
      all across the globe, with low latency, high transfer speeds.
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
    
  - Shield 
    - Managed DDoS protection service.
      that safeguards applications running on AWS.
    - 2 tiers of support - Standard and Advanced. Standard is automatic,
      at no additional charge.

  - Web Hosting
    - Provides low-cost ways to deliver websites and web applications.
    - Use cases include a marketing, rich-media or ecommerce website. 
    - Types:
      - Single Page Web App Hosting
      - Simple Static Website Hosting
      - Enterprise Web Hosting
 
  - Inspector
    - Automated *security assessment service* that helps improve the 
      security and compliance of applications deployed on AWS.
    - Automatically checks applications for exposure, vulnerabilities,
      and deviations from best practices.
    - Similar to Nessus Scan product.


- Security - Access Control and Management
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
    - Makes it easy to centrally manage access to multiple AWS accounts,
      business applications and provide users with SSO access to all 
      their assigned accounts.
    

