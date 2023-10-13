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

<img src="">

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









































































