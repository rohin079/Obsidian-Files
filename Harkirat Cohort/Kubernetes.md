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

![[Pasted image 20241111163604.png]]

a deployment actually creates a replicaset that creates the replicaset

replicasets: 

A ReplicaSet in Kubernetes is a controller that ensures a specified number of pod replicas are running at any given time. It is used to maintain a stable set of replica Pods running in the cluster, even if some Pods fail or are deleted.

When you create a deployment, you mention the amount of `replicas` you want for this specific pod to run. The deployment then creates a new `ReplicaSet` that is responsible for creating X number of pods.

whenever we update a deployment and reapply it, it first creates another replicaset, which in turn tries to create new pods, and if those pods work, it slowly moves the traffic from old replicaset to new one, similar to blue green deployments

# Services

In Kubernetes, a "Service" is an abstraction that defines a logical set of Pods and a policy by which to access them. Kubernetes Services provide a way to expose applications running on a set of Pods as network services. Here are the key points about Services in Kubernetes:

Key concepts

1. **Pod Selector**: Services use labels to select the Pods they target. A label selector identifies a set of Pods based on their labels.

2. **Service Types**:

- **ClusterIP**: Exposes the Service on an internal IP in the cluster. This is the default ServiceType. The Service is only accessible within the cluster.

- **NodePort**: Exposes the Service on each Node’s IP at a static port (the NodePort). A ClusterIP Service, to which the NodePort Service routes, is automatically created. You can contact the NodePort Service, from outside the cluster, by requesting `<NodeIP>:<NodePort>`.

- **LoadBalancer**: Exposes the Service externally using a cloud provider’s load balancer. NodePort and ClusterIP Services, to which the external load balancer routes, are automatically created.

3. **Endpoints**: These are automatically created and updated by Kubernetes when the Pods selected by a Service's selector change.

- Create service.yml

```javascript
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
      nodePort: 30007  # This port can be any valid port within the NodePort range
  type: NodePort
```

- Restart the cluster with a few extra ports exposed (create kind.yml)

```javascript
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 30007
    hostPort: 30007
- role: worker
- role: worker
```

- kind create cluster --config kind.yml

- Re apply the deployment and the service

- Visit `localhost:30007`

![notion image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F085e8ad8-528e-47d7-8922-a23dc4016453%2Fefabe5a1-bac7-4b64-bbb6-e482c1f426a7%2FScreenshot_2024-06-01_at_5.05.13_PM.png?table=block&id=2692c080-a889-4465-aa27-6f7330fcb2d4&cache=v2)

Read about types of services -

NodePort
ClusterIP 
LoadBalancer service


best way - load balancer. Also the loadbalancer runs outside by kubernetes cluster.


read about downsides of load balancers - 

### Ingress

The `kube-controller-manager` runs a bunch of `controllers` like

1. Replicaset controller

2. Deployment controller

etc

If you want to add an `ingress` to your kubernetes cluster, you need to install an `ingress controller` manually. It doesn’t come by default in k8s

![[Pasted image 20241201004726.png]]

![[Pasted image 20241201004908.png]]

### Namespaces

In Kubernetes, a `namespace` is a way to divide cluster resources between multiple users/teams. Namespaces are intended for use in environments with many users spread across multiple teams, or projects, or environments like development, staging, and production

When you do

```javascript
kubectl get pods
```

it gets you the `pods` in the `default` namespace

#### 

[](https://projects.100xdevs.com/tracks/kubernetes-part-2/Kubernetes-Part-2-9#2a1e6198db4543ff80beb88a38ffbed6 "Creating a new namespace")Creating a new namespace

- Create a new namespace

```javascript
kubectl create namespace backend-team
```

- Get all the namespaces

```javascript
kubectl get namespaces
```

- Get all pods in the namespace

```javascript
kubectl get pods -n my-namespace
```

- Create the manifest for a deployment in the namespace

```javascript
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  namespace: backend-team
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

- Apply the manifest

```javascript
kubectl apply -f deployment-ns.yml
```

- Get the deployments in the namespace

```javascript
kubectl get deployment -n backend-team
```

- Get the pods in the namespace

```javascript
kubectl get pods -n backend-team
```

- Set the default context to be the namespace

```javascript
kubectl config set-context --current --namespace=backend-team
```

- Try seeing the pods now

```javascript
kubectl get pods
```

- Revert back the kubectl config

```javascript
kubectl config set-context --current --namespace=default
```


### Helm 

Helm is package manager for k8's

![[Pasted image 20241201013030.png]]











