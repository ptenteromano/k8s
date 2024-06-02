# DevOps, Docker, K8s, Helm

Repository to brush up and improve my devops skills. Contains code for multiple courses and resources. Documentation is available in the respective directories (most of the time).

Using multiple minikube 'profiles':
```bash
minikube start -p c1 &
minikube start -p c2 &

minikube profile list
kubectl get deploy -A --context c1
kubectl get deploy -A --context c2
```

### /bootdev_docker
Code for the bootdev course on docker. Contains a load balancer, Go server and a python script. Docker building, managing, running, and publishing.

### /bootdev_k8s
Code for the bootdev course on k8s. Contains web, api and crawler configurations. K8s deployments, services, configmaps, and ingress, namespaces, etc.
