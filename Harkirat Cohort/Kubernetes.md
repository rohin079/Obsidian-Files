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

used kind to start a cluster with a custom config file for starting 3 nodes which are essentially 3 docker images- 1 master + 2 worker

interact with this master node using kubectl

create a pod: 

```
➜  ~ kubectl run nginx --image=nginx --port=80
pod/nginx created
➜  ~ 

```

like how we run docker containers by docker run command, we are running kubectl commands which sends a request to your API server

do delete a pod:
```
kubectl delete pod nginx
```

Manifest files for running a pod using config:

![[Pasted image 20241111143746.png]]

Deployments:

![[Pasted image 20241111155025.png]]


```
kubectl 
```

deployments take care of starting the pods, rolling them back, updating pods, bringing them back up, roll back capabilities

A Deployment is a higher-level controller that manages a set of identical Pods. It ensures the desired number of Pods are running and provides declarative updates to the Pods it manages.

you can make a deployment by either running a single command or making a manifest file like deployment.yml