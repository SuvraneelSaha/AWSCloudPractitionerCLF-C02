```
IAM - Identity Access Management 
```

~~~
• IAM = Identity and Access Management, Global service
• Root account created by default, shouldn’t be used or shared
• Users are people within your organization, and can be grouped
• Groups only contain users, not other groups
• Users don’t have to belong to a group, and user can belong to multiple groups
~~~

~~~
IAM: Permissions
• Users or Groups can be
assigned JSON documents
called policies
• These policies define the
permissions of the users
• In AWS you apply the least
privilege principle: don’t give
more permissions than a user
needs 
~~~

~~~
IAM is a global service 
~~~

~~~
IAM Setup
~~~

~~~
1. Login to the aws root account 
2. go to the iam service 
3. create a user group with adminstrator access ; 
4. add a user with an example name 
5. add that user to that specific user group 
6. go to a private window and login to the iam account via the url that has been changed for the specifc user group 
7. OPEN side by side the root account and the IAM user account ; 

~~~
~~~
IAM Policies Structure
inline policy - means policy for a single specific person 
~~~
~~~

• Consists of • Version: policy language version, always include “2012
-10
-
17”
• Id: an identifier for the policy (optional) • Statement: one or more individual statements (required)
• Statements consists of • Sid: an identifier for the statement (optional) • Effect: whether the statement allows or denies access
(Allow, Deny)
• Principal: account/user/role to which this policy applied to • Action: list of actions this policy allows or denies • Resource: list of resources to which the actions applied to • Condition: conditions for when this policy is in effect
(optional)
~~~

~~~
POlicy Hands ON 

with read only access - we have reading capability only not anything else via the IAM user candidate ; 

1. if a person A belongs to 2 groups then the policies that have been assigned to that user Groups ; 
will be inherited by the person A 
2. You can make custom policies , and assign it to a Group or directly to that of a user via inline policy ; 

~~~

~~~
IAM – Password Policy

~~~
~~~
• Strong passwords = higher security for your account
• In AWS, you can setup a password policy:
• Set a minimum password length
• Require specific character types:
• including uppercase letters
• lowercase letters
• numbers
• non-alphanumeric characters
• Allow all IAM users to change their own passwords
• Require users to change their password after some time (password expiration)
• Prevent password re-use
~~~
~~~
Multi Factor Authentication - MFA
• Users have access to your account and can possibly change
configurations or delete resources in your AWS account
• You want to protect your Root Accounts and IAM users
• MFA = password you know + security device you own
• Main benefit of MFA:
if a password is stolen or hacked, the account is not compromised

~~~

~~~
MFA devices options in AWS
Virtual MFA devices present - 
Google Authenticator
(phone only)
Authy
(phone only)
these supports - Support for multiple tokens on a single device. 

Universal 2nd Factor (U2F) Security Key  
YubiKey by Yubico (3rd party) 
Support for multiple root and IAM users
using a single security key 

MFA devices options in AWS
Hardware Key Fob MFA Device 
Provided by Gemalto (3rd party) 

Hardware Key Fob MFA Device for
AWS GovCloud (US) 
Provided by SurePassID (3rd party)
~~~

~~~
MFA hands on - 
Password changing , and also using Multi factor authentication via Authenticator or physical security keys . 
Once done it will ask for MFA codes ; when logging in ; 
it is basically done for the root user ; 
and upto 8 accounts can be added via the MFA 
~~~

~~~
How can users access AWS ?
~~~

~~~
To access AWS, you have three options:
• AWS Management Console (protected by password + MFA)
• AWS Command Line Interface (CLI): protected by access keys
• AWS Software Developer Kit (SDK) - for code: protected by access keys
• Access Keys are generated through the AWS Console
• Users manage their own access keys
• Access Keys are secret, just like a password. Don’t share them
• Access Key ID ~= username
• Secret Access Key ~= password

~~~
~~~
What’s the AWS CLI?
~~~
~~~
A tool that enables you to interact with AWS services using commands in
your command-line shell
• Direct access to the public APIs of AWS services
• You can develop scripts to manage your resources
• It’s open-source [Link Text](https://github.com/aws/aws-cli)
• Alternative to using AWS Management Console

~~~

~~~
AWS ClI Hands ON 

same as the management console which is present in the aws console ; 

~~~

~~~
AWS Cloud Shell

Terminal in the cloud ; 
it is supported in many regions but not all the regions ; 
~~~

~~~
IAM Roles for Services  

Some AWS service will need to
perform actions on your behalf
• To do so, we will assign
permissions to AWS services
with IAM Roles
• Common roles: • EC2 Instance Roles • Lambda Function Roles • Roles for CloudFormation 

Example - EC2 instance which is a virtual server and it needs a set of permissions to start working ; 
and the permissions or set of permissions that is in this case is roles is assigned by the user itself ; 

~~~

~~~
IAM Role Hands ON 
~~~

~~~
IAM roles is given for the AWS Services ; 

Step 1 - create a role for an AWS Service ; 
Step 2 - Add the permissions / policies for that specific role 
Step 3 - Use the Aws Service with the role that is given 

~~~

~~~
IAM Security Tools
~~~

~~~
• IAM Credentials Report (account-level)
• a report that lists all your account's users and the status of their various
credentials
• IAM Access Advisor (user-level)
• Access advisor shows the service permissions granted to a user and when those
services were last accessed.
• You can use this information to revise your policies.
~~~

~~~
IAM Security Tools Hands ON 
~~~

~~~
Credentials report for IAM root user; 
It will give all the details of the changed or modified entities like the password change, last used , MFA present or not in a CSV file ; 

IAM Last Access report - gives information on the AWS Services that are used previously with which Permissions involved ; 
~~~

~~~
IAM Guidelines & Best Practices 
~~~

~~~
• Don’t use the root account except for AWS account setup
• One physical user = One AWS user
ie one user apart from that of the root 
your friend 1 user , YOU 1 user two different users . 
• Assign users to groups and assign permissions to groups
• Create a strong password policy
• Use and enforce the use of Multi Factor Authentication (MFA)
• Create and use Roles for giving permissions to AWS services
• Use Access Keys for Programmatic Access (CLI / SDK)
• Audit permissions of your account using IAM Credentials Report & IAM
Access Advisor
• Never share IAM users & Access Keys
~~~

~~~
Shared Responsibility Model for IAM
~~~

~~~
AWS : 
Infrastructure (global
network security)
• Configuration and
vulnerability analysis
• Compliance validation
~~~

~~~
User
• Users, Groups, Roles, Policies
management and monitoring
• Enable MFA on all accounts
• Rotate all your keys often ie the Access Keys over a time period 
• Use IAM tools to apply
appropriate permissions
• Analyze access patterns &
review permissions  
~~~

~~~
In simple words ; 
AWS is responsible for all things Infrastructure 
and User is responsible is Using the Infrastructure responsibly 
~~~