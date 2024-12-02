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

