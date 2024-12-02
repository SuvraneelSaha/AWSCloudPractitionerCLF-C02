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