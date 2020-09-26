# AWS Shield
* A managed DDoS (Distributed Denial of Service) protection service 
  that safeguards applications running on AWS.
* Provides always-on detection and automatic inline mitigations that
  minimize application downtime and latency, so there's no need to 
  engage AWS support for DDoS protection.

## 2 Levels:
### AWS Shield Standard
* Automatic protection, for all AWS customers, at no additional charge
  * Any AWS resource, region, etc.
  * Quick detection - always on
  * Inline attack mitigation
    * Built-in automated mitigation techniques
    * Avoids latency impact
  * Self-service
    * No need to engage AWS support
### AWS Shield Advanced 
* Paid service for higher levels of protection, features and benefits.
  * Specialized support
    * 24x7 access to the AWS DRT (DDoS Response Team).
  * Advanced attack mitigation
    * AWS WAF
  * Visibility and attack notification
    * e.g. - HTTP floods, DNS query floods, etc.
  * Always-on monitoring
  * Enhanced detection
  * DDoS cost protection
    * If any of your services have to scale up due to an attack, AWS 
      will provide service credits for charges due to usage spikes.

## DDoS attack vs DoS attack:
  * A DoS attack is a deliberate attempt to make your website or app
    unavailable to users by flooding it with network traffic.
    * A variety of techniques that consume large amounts of network 
      bandwidth, or tie up other system resources are employed, thus
      disrupting access for legitimate users.
    * A lone attacker is doing so via a single source.
  * In a DDoS attack, the attacker is using multiple sources to
    orchestrate an attack against a target. Sources include, but are
    not limited to:
    * Malware-infected computers, routers, IoT devices, and other 
      endpoints.
    * Typically launched from a botnet of compromised computers.

  * Example attack:
    * Using a highly-targeted application layer attack, an attacker may
      go after a web page with less than 100 requests per second.
      * Customers use WAFs (Web Application Firewalls) to block these
        requests before they reach the web server infrastructure.

* DDoS mitigation challenges
  * Mitigating DDoS attacks is challenging:
    * Complex setup and implementation
    * Bandwidth limitations
    * Manual intervention
    * Time consuming
    * Degraded performance
    * Expensive

* Benefits:
  * Cost efficient
  * Seamless integration and deployment
  * Customizable protection

  - Protecting your DNS
    - Using Amazon Route 53:
      - AWS Shield Standard - Hosted zones.
      - AWS Shield Advanced - Attack visibility, DRT support.

  - Proecting web applications and APIs
    - Using Amazon CloudFront or Application Load Balancer
      - AWS Shield Standard - Always on, scrubs bad traffic.
      - AWS Shield Advanced - DRT support, traffic engineering,
                              application layer protection.
  
  - For other custom applications not based on TCP (e.g., UDP, SIP):
    - You cannot use services like Amazon CloudFront or Elastic Load
      Balancing. In these cases, you often need to run your applications
      directly on internet-facing Amazon EC2 instances.
      - Using Elastic IP address:
        - AWS Shield Standard - Built-in techniques.
        - AWS Shield Advanced - Custom mitigation profiles, additional 
                              bandwidth

