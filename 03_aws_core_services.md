# AWS Core Services

## Amazon Elastic Cloud Compute (EC2)
* Pay as-you-go server resources, also called Amazon EC2 Instances. 
  * Use PuTTYGEN to open .pem file, then save the private key from there 
    in order to access the EC2 instance.

## Amazon Elastic Block Store (EBS)
* Pay as you use.
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

