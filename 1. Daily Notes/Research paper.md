https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/
### Control network access to sensitive ports[¶](https://cheatsheetseries.owasp.org/cheatsheets/Kubernetes_Security_Cheat_Sheet.html#control-network-access-to-sensitive-ports "Permanent link")

Kubernetes clusters usually listen on a range of well-defined and distinctive ports which makes it easier identify the clusters and attack them. Hence it is highly recommended to configure authentication and authorization on the cluster and cluster nodes.

Here is an overview of the default ports used in Kubernetes. Make sure that your network blocks access to ports and consider limiting access to the Kubernetes API server except from trusted networks.


Signcryption service
- hashing
- sign with client private key
Access control
-  where in k8s
- how to verify
	- cappability list (JSON file)
	- parralell agenthttps://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/
	- how to interract with k8s
service for client to sign their private key

design protocol
model

## Kubernetes
- Node and Pod
	- node = simple server
	- pod = abstaction over container 
		-  smallest unit of k8s
		- 1 application per pod
		- has virtual ip address
		- communicate using ip address
		- ephremeral, re-creation with new ip address
	- service = permanent ip address to each ip address
		- seperate life cycle
		- ![[Pasted image 20230316094757.png]]
	- ingress = you want to access via https://my-app.com so it go through ingress first 
		- forwarding to a service
	- configmap = external configuration 
		-  no need to rebuild when you change the endpoint using in the app
	- secret = configmap for seccret data ex. mongo-pwd based64 encoded
	- volume = attach physical storage to the pod
		- can be local or remote




Integrity protection for kubernetes 
- Problems
	- If all unsigned requests from the cluster are blocked by the admission controller because of no signature, it may affect the cluster
		- Solution: 
			- The development of a flexible profile to efficiently filter requests and changes to the resource based on the internal cluster behavior from the signature verification and to control the admission request based on the profile.
	- It is not easy to verify the signature correctly at the admission controller because the Kubernetes resource is rewritten internally before the admission controller receives the signed Kubernetes resource.
		- Solution:
			- The development of an admission controller that verifies the signature of a Kubernetes resource in an admission request based on the object at the time of signature generatio
				- we utilize the DryRun [18] function of Kubernetes to calculate the consistency between the resource in the admission request and the resource at the time of signature creation so that the signature can be verified correctly based on the original resource
					- Dryrun => 
				- in order to achieve signature verification of Kubernetes resources at the admission controller, we should not verify the signature of the resource included in the admission request directly. Instead, we must take into account the parts that have been changed by the internal operation of the cluster