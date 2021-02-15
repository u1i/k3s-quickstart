# k3s Quickstart

## 1 – Install k3s

`curl -sfL https://get.k3s.io | sh -`

### Check for Ready node, 

takes maybe 30 seconds
`k3s kubectl get node`

until the output looks like this:
> NAME         STATUS   ROLES                  AGE   VERSION  
> instance-1   Ready    control-plane,master   72s   v1.20.2+k3s1



