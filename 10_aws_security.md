# Identity and Access Management
(Authentication and Authorization with AWS Identity and Access 
Management)
* USER
  * A permanent-named operator.
    * Can be human or machine.
    * My credentials are permanent and they stay with that named user
      until there is a forced rotation, whether it's a name and 
      password, access key, secret key combination, etc.
    * This is my authentication method for named users in the system.
    * Example - Allan the operator.
* GROUP
  * A collection of users! 
    * Example - The group of Administrators.
* ROLE
  * In AWS, a role is not your permissions. 
  * A role is an authentication method.
  * A role is also an operator, but the credentials are temporary.
  * Example - Developer for Project 17.
* POLICY DOCUMENT
  * Everything in AWS is an API. 
    * This means that to execute the API, we first have to 
      authenticate. We also have to authorize.
    * Since the role is not permissions (it is simply the auth method).
    * Permissions, in every case, happen in a separate object known as
      the Policy Document.
  * JSON document that can be attached to a user, group, or role.
  * Lists the specific API or wildcard group of APIs that I am 
    whitelisting, or allowing against a set of resources, conditions,
    etc.

## Process:
* An operator wants to put an object into an S3 bucket (this is an API 
  call)
* API is executed, which includes the object name, bucket name, 
  present a set of credentials, etc. 
    * All of this is called the API
  execution statement.
* The API execution statement gets presented to the AWS API engine.
* The AWS API (IAM) engine validates the credentials presented against 
  any one of the policy documents.
* All actions are by default, implicitly denied, unless that action
  has an 'allow' policy.
* An explicit deny overrides any allow statement.
  * You can use this where you want to permanently prevent certain
    actions from happening. 

* In the event that there's a compromise of security credentials, the
  security manager - who may not know which account got compromised -
  can execute a single API statement that removes every single policy
  document from all the users, groups and roles.
  * After the revocation of the policy documents, attempts to do 
    further compromise will be logged in CloudTrail.

