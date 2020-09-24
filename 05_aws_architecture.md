# AWS Well-Architected Framework

## 5 Pillars
* Security
* Reliability
* Performance efficiency
* Cost optimization
* Operational excellence

## Security Pillar
* Cloud security is composed of five areas:
  * Identity and access management (IAM)
    * Ensures that only authorized and authenticated users are able to
      access your resources - only in the manner that you intend.
  * Detective controls
    * Can be used to identify a potential security incident by
      considering approaches such as capturing or analyzing logs and
      integrating auditing controls.
  * Infrastructure protection
    * Ensures that systems and services within your architecture are
      protected against unintended and unauthorized access.
  * Data protection
    * Data classification, encryption, protecting data at rest and in
      transit, backups, replication and recovery when needed.
  * Incident response
    * Even with all of the above in place, shit happens.
    * An incident response process can allow proper response and
      mitigates any potential security incidents.
    * Ensures that your architecture is updated to accomodate a timely
      investigation and recovery.

* Security Pillar: Design Principles
  * Implement (apply) security at all layers
  * Enable traceability
  * Apply principle of least privilege
  * Focus on securing your system
  * Automate
    * Automate security best practices.
    * Automate patched image deployment
    * Automate incident response for routine and anomalous security
      events.

## Reliability Pillar
* Recover from issues/failures
* Apply best practices in:
  * Foundations
    * Foundational requirements that influence reliability should be
      in place.
  * Change management
    * Important to fully understand and be aware of how change can
      affect your system.
  * Failure management
    * Automation is key here.
    * Systems should automatically be able to detect failures and do
      self-healing.
    * Antipate, respond to, and prevent failures

* Reliability Pillar: Design Principles
  * Test recovery procedures
    * Test how your systems fail.
  * Automatically recover (from failure)
    * In AWS, you're able to trigger automatic responses when thresholds
      are breached.
  * Scale horizontally
    * Replace a large (monolithic) resource with multiple small
      resources. This will reduce the impact of a single point of
      failure on the overall system.
  * Stop guessing capacity
    * Monitor system demand/utilization, then automate the addition
      and/or removal of resources.
  * Manage change in automation
    * Changes in your architecture and infrastructure should be made
      using automation. With this, you only need to manage change in
      your automation, and not on every single resource.

## Performance Efficiency Pillar
* Select customizable solutions
  * Go with the best solution that will optimize your architecture.
  * Get the right tool for the right job.
* Review to continually innovate
  * Continually innovate your solutions and take advantage of newer
    technologies that become available.
* Monitor AWS services
  * After you have implmented your architecture, it is important to
    monitor performance to ensure that you can remediate any issues
    before your customers become aware of them.
* Consider the trade-offs
  * For example, trading consistency, durability, and space versus
    time or latency, in order to ensure that you deliver higher
    performance.

* Performance Efficiency Pillar: Design Principles
  * Deocratize advanced technologies
    * Difficult-to-implement technologies can be simpler to consume by
      pushing that knowledge and complexity into the cloud vendor's
      domain.
      * Instead of having your IT team learn how to host and run a new
        technology, they can consume it as a service.
  * Go global in minutes
  * Use serverless architectures
    * Removes the operational burden, OS layer, and controls costs.
  * Experiment more often
    * With virtualization, you can carry out testing to enhance your
      efficiency.
  * Have mechanical sympathy
    * Use the technology approach that best aligns with what you're
      trying to achieve.

