
Signcryption service
- hashing
- sign with client private key
Access control
-  where in k8s
- how to verify
	- cappability list (JSON file)
	- parralell agent
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