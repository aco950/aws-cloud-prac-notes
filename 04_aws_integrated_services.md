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

