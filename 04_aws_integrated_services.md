# AWS Integrated Services
* Remember that every AWS service that you learn about is another tool 
  to build solutions. The more tools you can bring to the table, the 
  more powerful you become. 

## Application Load Balancer
* Part of the Elastic Load Balancing Service (2nd edition)
* Replaces Classic Load Balancer
* Adds supported protocols, CloudWatch Metrics, Access Logs, and Health 
  Checks.
* Use cases:
  * Use containers to host microservices and route to those services 
    from a single load balancer.
  * Route requests based on content.
* Key Terms:
  * Listener 
    * A process that checks for connection requests using the protocol 
      and port that you configure.
  * Target 
    * Destination for traffic based on the established listener rules.
    * The Application Load Balancer registers Targets instead instances.
  * Target Group 
    * Routes requests to one or more of the registered targets using the 
      protocol and port number specified.
    * The Target Group is how the Targets are registered to the 
      Application Load Balancer.

* NOTE: You'll need to select 2 AZs when setting this up.

## Auto Scaling
* Helps you ensure that you have the correct number of Amazon EC2
  instances available to handle the load for your application.
  * This is based on conditions that you specify.
* Removes the guesswork of figuring out how many instances you need at a 
  point in time in order to meet your workload requirements.
* When running your applications on EC2 instances, you should monitor 
  the performance of your workload via Amazon CloudWatch.
  * With CloudWatch, you can measure your workload and see when demand 
    is highest/lowest.
* Answers 2 questions:
  * How can I ensure that my workload has enough EC2 resources to meet
    fluctuating performance requirements? (Scalability)
  * How can I automate EC2 resource provisioning to occur on-demand?
    (Automation).
    * NOTE: 2 very important AWS tenets:
      * Make your environment scalable.
      * Automate as much as possible.
  * Advantages:
    * Better cost optimization (you are not running a full fleet when
      things are slow).
      * Scale **out** to meet performance needs/demands.
      * Scale **in** to save money.
    * Avoids your application from timing out and underperforming.
  * Process:
    * Start with a Base Configuration.
    * Launching instances is the process of Scaling Out.
    * Terminating instances is the process of Scaling In.
  * Components:
    * Launch Configuration
    * Auto Scaling Group
    * Auto Scaling Policy
  * Dynamic Auto Scaling
    * Create CloudWatch alarms based on performance info from EC2
      instances or a load balancer.
    * When a performance threshold is breached, a CloudWatch alarm
      triggers an Auto Scaling even which either scales out or scales
      in.

## Amazon Route 53
* A global, highly-available DNS web service designed to provide 
  business and devs with a reliable and highly scalable way to route end 
  users to internet applications.
* A managed DNS solution, instead of deploying your own DNS server.
* Requires you to have a domain name purchased via a registrar.
* You can have external or internal hosted zones.
* Can also do domain registration (as a registrar).
* Other DNS Resolution Strategies:
  * Simple routing
  * Weighted round-robin
  * Geo-location
  * Latency-based
  * Failover
  * Multi-value answer

## Amazon Relational Database Services (RDS)
* Amazon RDS is a managed service that sets up and operates a relational 
  database in the cloud
* Provides cost-efficient and resizable capacity while automating the
  following administrative tasks:
  * Challenges of Relational Databases
    * Server maintenance and energy footprint
    * Software installation and patches
    * Database backups and high availability
      * High availabilty via Multi-AZ
    * Scalability limits
    * Data security
    * OS installations and patching
* Frees you to focus on your application.
* You manage application optimization, while AWS manages the rest.
* Basic building block of Amazon RDS is the database instance.
* Use Cases:
  * Web and Mobile Apps
  * E-commerce Apps
  * Mobile and Online Games

## AWS Lambda
* Function as a Service
* Fully-Managed serverless compute
  * No servers to manage
* Event-driven execution
* Sub-second metering
* Multiple (programming) languages supported
* Executes your code only when needed
  * You only pay when your code is running, not during downtime
* We can run code for any application or backend service
* Use Cases:
  * Automated backups
  * Processing objects uploaded to S3
  * Event-driven log analysis
  * Event-driven transformations
  * Internet of Things (IoT)
  * Operating serverless websites
  * Real-time stream processing (with Amazon Kinesis)
  * Extract/Transform/Load pipeline
  * API Gateway
  * Web Backends

## AWS Elastic Beanstalk
* Platform as a Service
* Allows you to quickly get your application into the cloud.
* Allows quick deployment of your applications
  * You can update your application later on, just as easily as you 
    deployed it
* Reduces management complexity
* Keeps control in your hands:
  * Choose your instance type
  * Choose your database
  * Set and adjust Auto Scaling

## Amazon Simple Notification Service (SNS)
* Flexible, fully-managed pub/sub messaging and mobile communications
  service.
* Coordinates the delivery of messages to subscribing endpoints and
  clients.
* Easy to set up, operate and send reliable communications.
* Allows for the decoupling and scaling of microservices, distributed
  systems and serverless applications.
* Allows microservices to talk to one another.
* Allows for event notifications to be sent.
* Steps:
  * Create a topic
  * Create platform application
  * Create a subscription
  * Publish message
  * Publish text message (SMS)

## Amazon CloudWatch
* A real-time monitoring service for your AWS resources and the 
  applications you run on AWS.
  * Collect and track metrics
  * Collect and monitor log files
  * Set alarms on any of your metrics
    * Alarms watch a single metric.
  * Automatically react to changes
* Use cases:
  * Respond to state changes in your AWS resources.
  * Automatically invoke an AWS Lambda function to update DNS entries
    when an event notifies that an EC2 instance enters a running
    state.
  * Direct specific API records from CloudTrail to a Kinesis stream
    for detailed analysis of potential security or availability risks.
  * Take a snapshot of an Amazon EBS volume on a schedule.
  * Log S3 object level operations using CloudWatch events.
  * You can publish your own metrics, for an additional fee.
  * Detect and automatically revoke unintended IAM access with via a 
    CloudWatch event.
  * CloudWatch logs can be used for real-time troubleshooting.
    * Can also be archived.
    * Events are audited/logged (you can see who did what and when).
  * Dashboards for visualization

## AWS CloudFormation
- Simplifies the task of repeatedly and predictably creating groups of
  related resources that power your applications.
- All about automating resource provisioning.
- Fully-managed service, no infrastructure to support.
- Create, update and delete resources and sets known as 'stacks'.
  - Stacks are also a unit of deployment.
  - Template files become a form of self-documentation
  - Resources can be created based on dependencies
  - Templates become Infrastructure as Code
- For those new to this, you can get started easily with CloudFormation 
  Designer
- Requirements:
  - Templates
  - Permissions

