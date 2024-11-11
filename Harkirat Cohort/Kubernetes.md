Start multiple machines in a cluster with some worker machines and  some master machines.

![[Pasted image 20241030232758.png]]

a kubernetes cluster runs multiple nodes, nodes can be of two types - worker node or master node.

each worker node can run multiple pods and pods run containers 

![[Pasted image 20241030233012.png]]

## inside master Node -

1. etcd - it is a distributed key value pair datastore. when a user sends a desired state lets say 2 backend instances of a given image, the API server will store the desired state in etcd like :

{
	pod1 {
			image: backend_image
		},
	pod2 {
			image: backend_image
		}
}

2. scheduler - run an infinite loop to keep checking etcd to see if all pods have been assigned a worker or not and will assign a worker if a pod is pending

3. controller manager - runs an infinite loop to check if the deployment controller, jobs controller or RS controller need to do something. runs a bunch of controller
## Inside worker node - 

1. kublet - small process running inside each worker node checking if there is a pod you need to deploy or not, keep polling the master node

2. kube-proxy -  
3. 