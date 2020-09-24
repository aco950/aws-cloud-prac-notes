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

