# Elastic Compute Cloud 
~~~
AWS Budget Setup 
~~~

~~~
when setting up a budget we need to keep in consideration 
1. Free tier usage 
2. No of Services running 
3. Budget of whatever amount you have set the limit for 

The budget and billing can be done either from the Root or from IAM users with adminstrative permissions 
only if the root has changed the IAM users to access the billing issues via. 
Also you will get emails when the usage surpasses the usage 

~~~

~~~
Iam users and role access to billing information 
~~~

~~~
Bills give the detailed structured breakdown on how the charges are being done 

~~~

~~~
EC2 Basics 
~~~
~~~
EC2 is one of the most popular of AWS’ offering
• EC2 = Elastic Compute Cloud = Infrastructure as a Service
• It mainly consists in the capability of :
• Renting virtual machines (EC2)
• Storing data on virtual drives (EBS)
• Distributing load across machines (ELB)
• Scaling the services using an auto-scaling group (ASG)
• Knowing EC2 is fundamental to understand how the Cloud works
~~~

~~~
EC2 sizing & configuration options
~~~

~~~
Operating System (OS): Linux, Windows or Mac OS
 • How much compute power & cores (CPU) 
 • How much random-access memory (RAM) 
 • How much storage space: 
 • Network-attached (EBS & EFS) 
 • hardware (EC2 Instance Store) 
 • Network card: speed of the card, Public IP address 
 • Firewall rules: security group 
 • Bootstrap script (configure at first launch): EC2 User Data 
~~~

~~~
EC2 User Data
~~~

~~~~
• It is possible to bootstrap our instances using an EC2 User data script.
• bootstrapping means launching commands when a machine starts
• That script is only run once at the instance first start
• EC2 user data is used to automate boot tasks such as:
• Installing updates
• Installing software
• Downloading common files from the internet
• Anything you can think of
• The EC2 User Data Script runs with the root user
~~~~