# k3s Quickstart

You need:

* Virtual machine (on the cloud?) with 2GB RAM (or more)
* Operating System: Linux (Ubuntu / Debian / CentOS)
* Shell access as root

## 1 – Install k3s

`curl -sfL https://get.k3s.io | sh -`

### Check for Ready node, 

takes maybe 30 seconds

Run

`k3s kubectl get node`

until the output looks like this:
> NAME         STATUS   ROLES                  AGE   VERSION  
> instance-1   Ready    control-plane,master   72s   v1.20.2+k3s1

## 2 – Create a Service on Kubernetes

`k3s kubectl create deployment myapp --image=u1ih/hello`

### Show running pods and deployments
`k3s kubectl get pods --all-namespaces`

`k3s kubectl get deployments --all-namespaces`

## 3 – Expose Service

`k3s kubectl expose deployment myapp --port=8080 --type=LoadBalancer`

### List Services
`k3s kubectl get services --all-namespaces`

## 4 – Use the new Service

`curl localhost:8080`

> Hello, world!

><hr>Running on myapp-64c8f4d567-xlfrn

## 5 Scale up!

`k3s kubectl autoscale deployment myapp --min=5 --max=10`   

`k3s kubectl get deployment`

Run the curl command again a couple of times! Do you notice something?

`curl localhost:8080`

## 6 – Clean Up

`k3s kubectl delete deployment my-app`
`k3s kubectl delete service my-app`
