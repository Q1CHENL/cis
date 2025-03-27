## Automation
(to avoid human error)
### Levels of Automation
- Level 0: no automation (manual operation)
- Level 1: automated preparation and configuration (creation, deployment of vm)
- Level 2: automated monitoring and measurement (workload)
- Level 3: automated analysis of trends and prediction
- Level 4: automated identification of root causes
- Level 5: automated remediation of problems
## Orchestration: Managing containers
- orchestration software automates heterogeneous containers configuration and deployment
	- scaling
	- coordination
	- recovery
	>cloud is the computer, orchestration software is the OS

### Kubernetes (k8s)
- open source platform managing containerized workloadsa and services
### Functionalities
1. service naming and discovery (deploy, domain, ip)
2. load balancing (divide requests among instances of the service)
3. storage orchestration (host, private NAS (NFS), public NAS (EBS))
4. optimized container placement (virtual, physical)
5. automated initiation and recovery (of containers)
6. management of configuration and secrets (separation of config and management info and container images)
7. automated rollouts and rollbacks (new version)
### Limit (does not do)
- specific application optimization
- manage source code or build containers (docker does it)
- supply event passing middleware
- have a built in facility to collect/log/report measurements or events
> too complex, lousy documentation

![[Pasted image 20250327103035.png]]
#### A Kubernetes Cluster
- a set of replicated containers
- a set of support software
#### Kubernetes Pods
- a min. set of containers for an instance of an application (smallest unit of work)
- share an IP
#### Init containers
- perform initialization
- check the environment
#### Node: a physical/virtual server
- control panel (master) node
- worker node
- each cluster: one control panel node and multiple worker nodes
#### Software components
- API server (control panel)
- Scheduler (choose node)
- Cluster State Store (state info)
- Controller Manager (operate cluster)
- Cloud Controller Manager (cloud provider interactions)
- kubectl (cmdline interface to manage cluster)

![[Pasted image 20250327104621.png]]
![[Pasted image 20250327105131.png]]
#### Additional facilities
- replicas
- deployments
- stateful sets
- DaemonSet
- Garbage collection
- time to live controller
- job facility
- cronjob facility
- services facility

### Orchestration assessment
- + efficiency
- + coordination
- + avoid human errors
- - system wide cascading failure
- - risk of run-away resource use
- - increased security attack
- - complexity and overlapping functionality

### Orchestration in AWS
- Amazon Elastic Kubernetes Service (EKS): 0.10/hour, run on EC2/Fargate
- Amazon Elastic Container Service (Amazon ECS): proprietary, no extra charge