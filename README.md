- 👋 Hi, I’m @Nikhil9793
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Nikhil9793/Nikhil9793 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# VPC-VIRTUAL PRIVATE CLOUD (ISOLATED NETWORK)

A virtual private cloud (VPC) is a virtual network dedicated to your AWS account. It is logically isolated from 
other virtual networks in the AWS Cloud. You can launch your AWS resources, such as Amazon EC2 instances, into your 
VPC.

![image](https://github.com/user-attachments/assets/bb68b8b6-f837-4b36-835c-1c4de4df0e90)

**AWS Console -> Services -> Networking & Content Delivery -> VPC -> Your VPCs**

*VPC NAME: MYVPC*

*IPV4 CIDR BLOCK: 10.0.0.0/16*

# 1)CREATE VPC

![v1](https://github.com/user-attachments/assets/55c22b51-b445-4dfb-a0a0-3f41c8e17be5)

# 2)CREATE SUBNETS

![v2](https://github.com/user-attachments/assets/8d0762e0-9a24-40a3-9491-94a0f2874443)

# 3)CREATE INTERNET GATEWAY AND ATTACH TO VPC

An internet gateway is a horizontally scaled, redundant, and highly available VPC component 
that allows communication between instances in your VPC and the internet. It therefore imposes no availability risks or 
bandwidth constraints on your network traffic.

*Attach to S3 and S4, after attach S3 and S4 become public subnets.*  

![v3](https://github.com/user-attachments/assets/c3088226-ab31-4548-a781-d3584a6be560)

![v4](https://github.com/user-attachments/assets/ea5b1f86-9b6f-4212-91e7-00e10aca4411)

# 4)CREATE VIRTUAL PRIVATE GATEWAY

![v5](https://github.com/user-attachments/assets/f81bcad3-d560-4347-9604-ea8693fec53a)

# 5)CREATE ROUTE TABLES AND ATTACH TO SUBNETS

Route Tables. A route table contains a set of rules, called routes that are used to determine where network 
traffic is directed. Each subnet in your VPC must be associated with a route table; the table controls the routing for the 
subnet.

One route for Internet gateway, another for Virtual private gateway 

*Route - 0.0.0.0/0 to IGW* 

*Route - 192.168.0.0/16 to VGW*

![v6](https://github.com/user-attachments/assets/4f2bc041-3474-470c-a1c6-488afb646531)

![v7](https://github.com/user-attachments/assets/1f2190ca-3ff2-411b-9578-bb5f33fd3a31)

*Attach routing tables to subnets. R1-IGW to S3-Public and S4-Public, public network required to have internet access. Attach R2-VGW to S1-Private and S2-Private (No internet become a private subnets)*

# 6)CREATE INSTANCES

• Now we have to create two instnaces where we have to enable the public IPv4 .

•Then on both instance we have to downlaod the web server here i have downlaoded the apache2 server

*After that i checK that my instances are working or not .*

![v8](https://github.com/user-attachments/assets/bcd1399c-b520-437e-bc90-0ee12c22f0dc)

# 7)CREATE AWS ELASTIC LOAD BALANCER(ELB).

![image](https://github.com/user-attachments/assets/baaa72b6-ef5e-4844-8bc5-8f0ae0d50697)

Elastic Load Balancing (ELB) is a load-balancing service for Amazon Web Services (AWS) deployments. ELB automatically 
distributes incoming application traffic and scales resources to meet traffic demands. 

A Managed Load Balancing service 
 Distributes load incoming application traffic across multiple targets, such as amazon EC2 instances, containers, and 
IP Addresses 

 Recognizes and responds to unhealthy instances 

 Can be public or internal-facing 

 Uses HTTP, HTTPS, TCP, and SSL Protocols 

 Each Load Balancer is given a public DNS name 

*Internet-facing load balancers have DNS names which publicly resolve to the public IP Addresses of the load 
balancer of the load balancers nodes*

*Internal load balancers have DNS names, which publicly resolve to the private IP Addresses of the load 
balancers nodes.*

# HOW TO CREATE LOAD BALANCER

*We have to create the target group where we have to select the two insatance we have create then we have to go to helath check edited option which was present below the load balancer is create ,then edit it as given below image*

![v9](https://github.com/user-attachments/assets/e72244c3-ce54-47ab-9f6d-a2455a51c65c)

*•After that come to load balancer, where we have to select the target group which we have created then make the load balancer , it will look like the given image below .*

![v10](https://github.com/user-attachments/assets/3f76c674-4a22-43d1-bd5a-55c556ab6cfe)

![v11](https://github.com/user-attachments/assets/f13c9de8-b384-45f0-92a8-bfdbd316963f)

*Now we need to put any one  instance on running and then we need to write the following commands in putty -*

**htop**

**seq 999999999999999999999999999999999999999999999999999999999 > /dev/null &**

**htop**
