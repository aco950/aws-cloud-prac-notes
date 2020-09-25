# AWS Shared Responsibility Model
* Both you and AWS are ultimately responsible for securing your own
  application.
* Some parts, you are responsible for, while other parts, AWS is 100%
  responsible for. Understanding where that division is, is part of
  the interaction between you and AWS. 
  * User Data (YOU - AWS cannot see the user data)
  * Application (YOU - AWS cannot see what apps you're running)
  * Guest OS (YOU - AWS cannot see what guest OS you're running)

##(above this line, YOU are 100% responsible)

-------------------------------- EC2 instance --------------------------

##(below this line, AWS is 100% responsible)

  * Hypervisor
    * Was run on Xen (not sure if this is still current).
    * AWS made changes to this model that make it secure, and scalable
      so it can run a million concurrent customers, all without worry
      of data leakage.
  * Network (AWS)
    * AWS network, running proprietary networking protocols designed
      to allow security of your systems, so VPCs can run at scale, at
      velocity, etc. AWS does not tell you as part of their security.
    * While Amazon can't tell you what they do, they have told 
      auditors very specifically what they do.
      * https://aws.amazon.com/compliance
  * Physical (AWS)
    * Iron, concrete, barbed-wire fence, parking lot, physical 
      devices, etc. No public tours given for their data centers.
    * While Amazon can't tell you what they do, they have told 
      auditors very specifically what they do.
      * https://aws.amazon.com/compliance
  
* The parts that you are responsible for are protected by your data
  access keys, encryption methods, etc. AWS couldn't read it even if
  they wanted to.
  * A myth is that AWS is trolling through your info.
  * Because of the way AWS is architected, they couldn't get to it 
    even if they were allowed to, simply impossible to read.

