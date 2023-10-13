# AWS ELB

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/elb_instances_1.png">

Elastic Load Balancing automatically distributes your incoming traffic across multiple targets, such as EC2 instances, containers, and IP addresses, in one or more Availability Zones. 

## Benifits of ELB
1. A load balancer distributes workloads across multiple compute resources, such as virtual servers. Using a load balancer increases the availability and fault tolerance of your applications.
   
2. You can add and remove compute resources from your load balancer as your needs change, without disrupting the overall flow of requests to your applications.
   
3. You can configure health checks, which monitor the health of the compute resources, so that the load balancer sends requests only to the healthy ones. 

## Types of ELB
+ Application Load Balancers
+ Network Load Balancers
+ Gateway Load Balancers 
+ Classic Load Balancers. 

## Regions & Availability Zones
Region is a separate geographic area.

Availability Zones are multiple, isolated locations within each Region.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/reg%26avail.png">

## How ELB Works
+ A load balancer accepts incoming traffic from clients and routes requests to its registered targets (such as EC2 instances) in one or more Availability Zones.
+ The load balancer also monitors the health of its registered targets and ensures that it routes traffic only to healthy targets.
+ When the load balancer detects an unhealthy target, it stops routing traffic to that target.
+ It then resumes routing traffic to that target when it detects that the target is healthy again.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/networking-load_balancing.png">

## Components of ELB
 * listeners, load balancer, and the target group

## Listeners
A listener is a process that checks for connection requests. It is configured with a protocol and port number for       connections from clients to the load balancer.You configure your load balancer to accept incoming traffic by specifying one or more listeners.

## Target Groups
+ Target groups route requests to individual registered targets, such as EC2 instances, using the protocol and port number that you specify. You can register a target with multiple target groups. 
+ Each target group is used to route requests to one or more registered targets. When you create each listener rule, you specify a target group and conditions.

## Rules
Every listener has a default action, also known as the default rule. The default rule cannot be deleted and is always performed last.

## Cross-zone Load Balancing
+ The nodes for your load balancer distribute requests from clients to registered targets.
+ When cross-zone load balancing is enabled, each load balancer node distributes traffic across the registered targets in all enabled Availability Zones.
+ When cross-zone load balancing is disabled, each load balancer node distributes traffic only across the registered targets in its Availability Zone.
  
<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/cross_zone_load_balancing_enabled.png">

If cross-zone load balancing is enabled, each of the 10 targets receives 10% of the traffic. This is because each load balancer node can route its 50% of the client traffic to all 10 targets.

If cross-zone load balancing is disabled:
   + Each of the two targets in Availability Zone A receives 25% of the traffic.
   + Each of the eight targets in Availability Zone B receives 6.25% of the traffic.
cross-zone load balancing is always enabled at the load balancer level. At the target group level, cross-zone load balancing can be disabled.

## Application Load Balancer
+ Application Load Balancers intelligently provide scalability, performance, and availability. They also guarantee that your servers are not overworked and are prepared to handle traffic spikes.
+ Application Load Balancer, aka ALB, is an Elastic Load Balancer or ELB on AWS. It operates at the application layer (the seventh layer) of the Open Systems Interconnection (OSI) model.
+ The Application Load Balancer distributes incoming HTTP and HTTPS traffic across multiple targets.

## Benefits of ALB
+ **Support for Path conditions:** You can configure your listener with rules that forward requests based on the URL in the request. This allows you to break down your application into smaller services (microservices) and route requests to the appropriate service based on the URL’s content.
+ **Support for Host conditions:** You can configure your listener with rules that forward requests based on the host field in the HTTP header. This allows you to route requests to many domains using a single load balancer.
+ Routing is supported based on request information such as HTTP header conditions and methods, query parameters, and source IP addresses.
+ You can send routing requests to numerous applications on a single EC2 server.
+ An instance or IP address can be registered with numerous target groups on a separate port.

## How to Create ALB

1. Sign into AWS Management Console:
<img src="https://github.com/Gitscooby/Images/blob/main/Ec2%20image%204.png">

2. Select your preferred Region. Select a region from the drop-down, the selection of the region can be done on the basis of the criteria discussed earlier in the blog.
<img src="https://github.com/Gitscooby/Images/blob/main/Ec2%20image%205.png">

3. Select ELB Service in Management console
   
<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/ELB_service.png">

4. Click Create LoadBalancer buttton
   
<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/CreateELB.png">

5. Choose ELB type and click create

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/ChooseELB.png">
  
6. Make Basic Configuration Name, Schema and IP Address Type

## Scheme
Scheme is the type of load balancer.
1. Internet-facing
2. Internal
+ If Scheme is internet-facing , the load balancer has a public DNS name that resolves to a public IP address.
+ If Scheme is internal , the load balancer has a public DNS name that resolves to a private IP address.
+ Both internet-facing and internal load balancers route requests to your targets using private IP addresses. Therefore, your targets don't need public IP addresses to receive requests from an internal or an internet-facing load balancer.

## IP Address Type
1. IPV4
2. Dual Stack
+ IPv4 if your clients use IPv4 addresses to communicate with the load balancer, or choose Dualstack if your clients use both IPv4 and IPv6 addresses to communicate with the load balancer.
+ If the load balancer is an internal load balancer, you must choose IPv4.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/Basic_conf.png">

7. Configure Network mapping section - Choose VPC and Availability Zones
   
## Mapping
+ Enable two or more Availability Zones, to increase the fault tolerance of your application.
+ Select one subnet per zone. If you enabled dual-stack mode for the load balancer, select subnets with associated IPv6 CIDR blocks.
  
<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/nwmapp.png">

8. Add Security Groups for Loadbalancer

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/sg.png">

9. Add Listeners and Routing info - Add a Target Group

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/listener_routing.png">

10. Create Target Group and adding our servers

   Click create target group button to start specifying group details

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/TGcreate.png">

+ Choose target Type - Instances, Ip Address, Lambda, ALB
+ Add Target Group Name
+ Add Protocol and ports
+ Choose IP address type
+ Select Our VPC and Protocol Version

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/TG1.png">
<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/TG2.png">

## Protocol version

By default, Application Load Balancers send requests to targets using HTTP/1.1. You can use the protocol version to send requests to targets using HTTP/2 or gRPC(HTTP-Hyper Text Transfer Protocol and gRPC-High Performance Remote Procedure calls) .

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/TG3.png">
Adding Health check path to store logs

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/TG4.png">
+ Register our intsances as targets only running instance are shown in the Page.
+ Select and include below option to add our instance.

+ Finally review our targets and create targets group.
  
<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/TG5.png">

Once target group was created continue with **Step 9**

11. Review our configuration and create it.

<img src="https://github.com/Vennilavan12/zen-class-devops-documentation/blob/main/010%20-%20AWS/img/Final.png">




12. 
13. 



























































