## Characterstic of cloud
1. Cloud uses a shared pool of resources
2.  Uses Internet techn. to offer scalable and elastic services. 
3. The term “elastic computing” refers to the ability of dynamically and on-demand acquiring computing resources and supporting a variable workload. 
4. Resources are metered and users are charged accordingly. 
5. It is more cost-effective due to resource-multiplexing. Lower costs for the cloud service provider are past to the cloud users.  
6. Data is stored: 
	1. in the “cloud”, in certain cases closer to the site where it is used.
	2. appears to the users as if stored in a location-independent manner. 
7. The data storage strategy can increase reliability, as well as security, and can lower communication costs. Management: 
8. The maintenance and security are operated by service providers. 
9. The service providers can operate more efficiently due to specialisation and centralisation.
   
## Cloud model
![[Pasted image 20230301000439.png]]
## Issue of cloud
1. Less Control 
	1. Many companies and governments are uncomfortable with the idea of their information located on systems they do not control. Providers must offer a high degree of security transparency to help put customers at ease.
2. Technology Immaturity 
	1. Lack of world-wide adopted Standards. Use of closed proprietary technologies. Lack of knowledge and trust. API Jungle. Legal uncertainties.
3. Data Security 
	1. Migrating workloads to a shared network and compute infrastructure increases the potential for unauthorized exposure. Authentication and access technologies become increasingly important
4. Security Management
	1.  Providers must supply easy controls to manage firewall and security settings for applications and runtime environments in the cloud.
5. Reliability
	1. High availability will be a key concern. IT departments will worry about a loss of service should outages occur. Mission critical applications may not run in the cloud without strong availability guarantees
6. Compliance
	1. Complying with SOX, HIPAA and other regulations may prohibit the use of clouds for some applications. Comprehensive auditing capabilities are essential
7. Vendor-lock in
	1. Interoperability constraints. Low level of portability of application and services based on cloud. Contract and exit strategies Limitations on sharing or transferring data

## Requirement of visualization why visualization
1. Performance isolation  
	- as we can dynamically assign and account for resources across different applications  
2. System security:  
	- as it allows isolation of services running on the same hardware 
3. Performance and reliability: 
	- as it allows applications to migrate from one platform to another 
4. The development and management of services offered by a provider
## Model of virtualization difference benfit or con
## Issue of VM
1. a defense mechanism at some layer can be disabled by malware running at a layer below it.
2. It is feasible to insert a rogue VMM, a Virtual-Machine Based Rootkit (VMBR) between the physical hardware and an operating system.
3. The VMBR can enable a separate malicious OS to run surreptitiously and make this malicious OS invisible to the guest OS and to the application running under it.
4. Under the protection of the VMBR, the malicious OS could: 
	1. observe the data, the events, or the state of the target system.  
	2. run services, such as spam relays or distributed denial-of-service attacks. 
	3. interfere with the application
## xen model
## xen 4.0  special 

## Mapreduce why
	parallel computations are difficult and complex to manage: § Race conditions, debugging, data distribution, fault-tolerance, load balancing.
## Step of mapreduce
![[Pasted image 20230301071443.png]]
![[Pasted image 20230301071517.png]]
## Problem of large scale data
	parallel computations are difficult and complex to manage: § Race conditions, debugging, data distribution, fault-tolerance, load balancing, etc

## Spark and spark why? is mapreduce enough
	Most current cluster programming models are based on acyclic data flow from stable storage to stable storage
	common cases that spark improve
	»Iterative algorithms (machine learning, graphs) 
	»Interactive data mining tools (R, Excel, Python)
## Batch procerssing rrdd how related
	RDD is a read-only, partitioned collection of records.
	
	RDDs: Resilient distributed datasets (RDDs) 
	» Immutable, partitioned collections of objects 
	» Created through parallel transformations (map, filter, groupBy, join, …) on data in stable storage »Can be cached for efficient reuse

## gfs hdfs how diffrence
![[Pasted image 20230301021048.png]]
## process related architecture  of it
![[Pasted image 20230301072211.png]]
![[Pasted image 20230301072241.png]]
## mesos omega
## monolistic why mesos why omega
## main concept

## kubernetes
	Kubernetes ("K8s" for short) is an open source solution for automating the deployment and dynamic scaling of containerized online applications. Kubernetes uses containers, a system in Linux that groups applications into logical units for centralized and secure management. Containers are designed to be ephemeral
## component model 
1. Pod
	1. Pods are simply the smallest unit of execution in Kubernetes, consisting of one or more containers, each with one or more application and its binaries.
2. API server
	1. contains various methods to directly access the Kubernetes
3. etcd
	1. works as backend for service discovery that stores the cluster’s state and its configuration
4. Scheduler
	1. assigns to each worker node an application
5. Controller manager
	1. Keeps track of worker nodes 
	2. Handles node failures and replicates if needed 
	3. Provide endpoints to access the application from the outside world
6. Cloud controller
	1. communicates with cloud provide regarding resources such as nodes and IP addresses
7. Kubelet
	1. talks to the API server and manages containers on its node
8. Kube-proxy
	1. load-balances network traffic between application components and the outside world
## how model interract
## objective of k8

## resource management understansd wc wc
## Bvt Sedf credit how differnece of these three 
1. BVT 
	1. The VM effectively “borrows” virtual time from its future and thus does not disrupt long-term CPU sharing
2. SEDF
3. Credit
	1. For each VM, the scheduler assigns a weight and a cap. 
		1. If cap is 0, then the VM can receive extra time (WC-mode) 
		2. If cap is non-0, it shows the max time it can receive (NWC) 2
	2. support global load balancing
	3. provide no cpu idle
## best fit of these 3
Web server: BVT
iperf: SEDF
disk: Credit