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

~~~
Creating an EC2 instance with EC2 user data to host a website / web server 
~~~
~~~
Step1 - 
create the EC2 instance 
2 
name it 
3 
what type of hardware is needed (choose specifically free ones)
4
ram and data storage 
5 
Network type 
6
7 Create a key pair for the SSH encryption so that the user can log into the cloud via the shell using the SSH keys 
User Data ; 
this is the portion where we can give the cloud a script which will get executed only once in the 
lifecycle of the EC2 instance ; 
8
Check the summary and launch the EC2 instance ;

~~~

~~~
After Launching 
there will be 
public IP address 
and 
private IP address 

public IP address will change once we stop the EC2 instance and again load it ; 

~~~

~~~
When launching we need to check that the http protocol given is as 
http not https otherwise it will go to an infinite load Screen time ; 

~~~

~~~
EC2 instance State - 
1 Terminate 
2 Stop 
if you stop an instance and start it later on ; 
the public ip address will change 
so for which we need to use the new public ip address to access to that of the web server ; 

But the private Ip address wont be changed even if the EC2 instance was stopped ; 

Terminate means ending the EC2 
~~~

~~~
EC2 - EC2 Instance Types - Overview 
~~~
~~~
You can use different types of EC2 instances that are optimised for
different use cases (https://aws.amazon.com/ec2/instance-types/)
• AWS has the following naming convention:

m5.2xlarge

m: instance class
• 5: generation (AWS improves them over time)
• 2xlarge: size within the instance class


~~~

~~~
EC2 Instance Types – General Purpose
• Great for a diversity of workloads such as web servers or code repositories
• Balance between:
• Compute
• Memory
• Networking
• In the course, we will be using the t2.micro which is a General Purpose EC2
instance
~~~

~~~
EC2 Instance Types – Compute Optimized
• Great for compute-intensive tasks that require high performance
processors:
• Batch processing workloads
• Media transcoding
• High performance web servers
• High performance computing (HPC)
• Scientific modeling & machine learning
• Dedicated gaming servers
~~~

~~~
EC2 Instance Types – Memory Optimized
• Fast performance for workloads that process large data sets in memory
• Use cases:
• High performance, relational/non-relational databases
• Distributed web scale cache stores
• In-memory databases optimized for BI (business intelligence)
• Applications performing real-time processing of big unstructured data
~~~

~~~
EC2 Instance Types – Storage Optimized
• Great for storage-intensive tasks that require high, sequential read and write
access to large data sets on local storage
• Use cases:
• High frequency online transaction processing (OLTP) systems
• Relational & NoSQL databases
• Cache for in-memory databases (for example, Redis)
• Data warehousing applications
• Distributed file systems
~~~

~~~
EC2 Instance Types: example
Instance vCPU Mem (GiB) Storage Network
Performance
EBS Bandwidth
(Mbps)
t2.micro 1 1 EBS-Only Low to Moderate
t2.xlarge 4 16 EBS-Only Moderate
c5d.4xlarge 16 32 1 x 400 NVMe SSD Up to 10 Gbps 4,750
r5.16xlarge 64 512 EBS Only 20 Gbps 13,600
m5.8xlarge 32 128 EBS Only 10 Gbps 6,800
t2.micro is part of the AWS free tier (up to 750 hours per month)
Great website: https://instances.vantage.sh 
~~~
