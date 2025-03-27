- start of modern era of cloud computing (2006)

## Amazon Elastic Compute Cloud (EC 2)
- does not support live migration: has to be stopped
- load balancer in front of compute nodes
- google cloud and azure support love migration
### Regions
- 27 physical locations of dc, prices vary, located across the globe: us, eu, asia etc
- round trip time between locations: 10ms ~ 200ms
### Availability Zone (AZ)
- AZ ≈ DC, latency within as low as 0.03ms
- 1 Region <-> several AZs: eu-central-1a, eu-central-1b, eu-central-1c 
### Choice considerations
- legal reasons
- network bandwidth cost
- network speed
- fault tolerance
- availability
### Internet Traffic Cost
- free inbound data transfer 
- outbound: $0.05-$0.09/GB (free since march 2024)
### Intra-AWS Transfer Cost
- free within same AZ (private IP)
- 0.01-0.02 across regions
- 0.01 in each direction in same region across AZs
### Placement groups
- little control over which machine to get
- placement groups offer some control
	- cluster
	- spread
	- partition
### Pricing Models
#### On demand
- most expensive
- per second pricing
- min. 1 minute
- no guarantee that a particular instance is available
#### Reserved Instance
- 1 or 3 years
- 50-70% savings
- upfront or monthly payment
- discount by saving plans: commitment of spending
	- compute saving plans
	- ec2 instance saving plans
#### Spot
- when on demand: sell unused capacity to flexible users: 60-70% discount
- never more expensive than on-demand
- price fluctuates overtime
- can run for weeks without interruption
- may be forcefully stopped at any point
#### Best strategy: probably a mix of models

## Service Level Agreements (SLAs)
- commit to quality standards (e.g 95% uptime per month)
- Monetary penalties: refund if monthly instance/region level availability below e.g 99.5%

### Burstable Instances
- occasional workload spikes, low average
- oversubscription: co-locate VMs, through hypervisor
- practical savings

## Lambda: FaaS
- code automatically assigned to compute hardware
- automatic scaling
- short invocations, not for long running (max. 15 min)
- called serverless, stateless
- container per function
- minimal linux
- fine grained pricing

## Fargate
- **container-based** compute service alternative to EC2
- for **Elastic Compute Cloud (ECS)** or **Elastic Kubernetes Service (EKS)**
- user assigns vCPU and RAM constraints (e.g 1 vCPU, 5GB RAM)
- min. 1 minute
- **spot and savings plan available**

vs. EC2
- + no manual instance management
- + finer cpu/ram granularity than EC2, coarser than lambda
- - slightly more expensive
- - requires ECS/EKS
- fewer HW options
compute vs. space tradeoff

## Storage

### Amazon elastic block store (EBS)
- virtual disk
- block device
- addtional volumes can be added
- Own network (SAN)
- replicated across multiple servers in one AZ
- size: 1GB - 16TB
### Simple Storage Service
- most important after EC2
- terminology
	- object = file
	- prefix = file path
	- bucket  (public/private) = named collections of files in a region
- https api: GET, PUT, LIST, DELETE, charged differently
- 21-25/TB/month
- 99.999999999% avail per object
- high consistency from 2020: always read up to date data 

## Other services
- AWS Marketplace: buy/sell 3rd party software and SaaS, subscription based, AWS takes fee
## EC Trends
- network, io are costing more now since nvme and hbm introduced
## CPU Stagnation
- moore's law is dead
- specialized HW becomes more attractive
### custom aws hardware
- cannot be bought: storage, security chip, NIC...

## Machine Learning
- extremely compute intensive
- AWS Trainium accelerator etc
- GPUs with EC2

### FPGA
- programmable HW, good for pipeline parallelism
- FPGA with EC2