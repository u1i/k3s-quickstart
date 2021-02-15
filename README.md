# k3s Quickstart

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

`kubectl run my-app --image=u1ih/hello --port=8080`

### Show running services/containers
`kubectl get pods --all-namespaces`

`kubectl get deployments --all-namespaces`

## 3 – Expose Service

`kubectl expose deployment my-app --port=8080 --type=LoadBalancer`

### List Services
`kubectl get services --all-namespaces`

## 4 – Use the new Service

curl commands :)

## 5 – Clean Up

`kubectl delete deployment my-app`
`kubectl delete service my-app`
