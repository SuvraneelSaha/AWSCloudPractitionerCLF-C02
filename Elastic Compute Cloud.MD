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
~~~
Great website: [link](https://instances.vantage.sh)

~~~
Security Groups and Ports OverView
~~~

~~~
Security Groups are the fundamental of network security in AWS
• They control how traffic is allowed into or out of our EC2 Instances.

Internet --> (EC2 Instance shielded by the Security Group) --> Inbound and Outbound traffic depends on the Security Group 
• Security groups only contain allow rules
• Security groups rules can reference by IP or by security group
~~~

~~~
Security Groups
Deeper Dive
~~~
~~~
Security groups are acting as a “firewall” on EC2 instances 
• They regulate: 
• Access to Ports 
• Authorised IP ranges – IPv4 and IPv6 
• Control of inbound network (from other to the instance) 
• Control of outbound network (from the instance to other)
~~~

~~~
Security Groups
Diagram
~~~
![diagram](./SecurityGroupDiagram.png)

~~~
Security Groups
Good to know
~~~

~~~
Can be attached to multiple instances
• Locked down to a region / VPC combination
• Does live “outside” the EC2 – if traffic is blocked the EC2 instance won’t see it
• It’s good to maintain one separate security group for SSH access
• If your application is not accessible (time out), then it’s a security group issue
• If your application gives a “connection refused“ error, then it’s an application
error or it’s not launched
• All inbound traffic is blocked by default
• All outbound traffic is authorised by default
~~~

~~~
Referencing other security groups
Diagram
~~~
![diagram](./InboundOutboundTrafficAllowanceExample.png)

~~~
Classic Ports to know
~~~
~~~
22 = SSH (Secure Shell) - log into a Linux instance
• 21 = FTP (File Transfer Protocol) – upload files into a file share
• 22 = SFTP (Secure File Transfer Protocol) – upload files using SSH
• 80 = HTTP – access unsecured websites
• 443 = HTTPS – access secured websites
• 3389 = RDP (Remote Desktop Protocol) – log into a Windows instance
~~~

~~~
Security Groups Hands ON 
~~~

~~~
So here is a very important tip for you.
Any time you see a timeout,
okay, this is a timeout
because it keeps on trying to connect
but it doesn't succeed
and then it will eventually fail, called a timeout.
So if you see a timeout when trying to establish any kind
of connection into your EC2 instances,
for example, if you try to SSH into it,
but there's a timeout,
or if you try to do an HTTP query,
but there's a timeout,
or if you try to do anything with it
and there is a timeout,
this is 100% the cause
of an EC2 security group.
~~~
~~~
So change the EC2 Security Groups accordingly to that of the EC2s ; 
and also we have the ability to make a Single security group and add it to different EC2 instances ; 

~~~

~~~
SSH Summary Table
~~~
~~~
For mac and linux users use ssh ; 
~~~

~~~
How to SSH into an EC2 instance from the linux terminal 

~~~

~~~
ssh -i (Name of the Pem file in which Access KEys are present).pem ec2-user@(public ip address)

the ip address will change when the instance is stopped or restarted ; 

we can close the connection via pressing cntrl + G ; 

or we can use exit ; 


~~~
~~~
SSH Troubleshooting

~~~

![img](https://img-c.udemycdn.com/redactor/raw/2019-10-23_14-53-48-cc1a033599952b0c25e1932ddfe1eb46.png)
~~~~
1) There's a connection timeout

This is a security group issue. Any timeout (not just for SSH) is related to security groups or a firewall. Ensure your security group looks like this and correctly assigned to your EC2 instance.
~~~


~~~

2) There's still a connection timeout issue

If your security group is properly configured as above, and you still have connection timeout issues, then that means a corporate firewall or a personal firewall is blocking the connection. Please use EC2 Instance Connect as described in the next lecture.



3) SSH does not work on Windows

If it says: ssh command not found, that means you have to use Putty

Follow again the video. If things don't work, please use EC2 Instance Connect as described in the next lecture



4) There's a connection refused

This means the instance is reachable, but no SSH utility is running on the instance

Try to restart the instance

If it doesn't work, terminate the instance and create a new one. Make sure you're using Amazon Linux 2



5)  Permission denied (publickey,gssapi-keyex,gssapi-with-mic)

This means either two things:

You are using the wrong security key or not using a security key. Please look at your EC2 instance configuration to make sure you have assigned the correct key to it.

You are using the wrong user. Make sure you have started an Amazon Linux 2 EC2 instance, and make sure you're using the user ec2-user. This is something you specify when doing ec2-user@<public-ip> (ex: ec2-user@35.180.242.162) in your SSH command or your Putty configuration



6) Nothing is working - "aaaahhhhhh"

Don't panic. Use EC2 Instance Connect from the next lecture. Make sure you started an Amazon Linux 2 and you will be able to follow along with the tutorial :)



7) I was able to connect yesterday, but today I can't

This is probably because you have stopped your EC2 instance and then started it again today. When you do so, the public IP of your EC2 instance will change. Therefore, in your command, or Putty configuration, please make sure to edit and save the new public IP.
~~~~

~~~
EC2 instance connect ; 
Connection via the EC2 instance connect without the use of ssh and access keys ; 
we can use it directly to connect to the EC2 instance ; 
port 22 is the default port for sshing into a remote virtual machine or an EC2 instance 

~~~