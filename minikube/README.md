## K8s with Minikube

Staring with bootdev k8s course

- Images
- Configmaps
- Deployments
- Services


#### Start up minikube
```bash
minikube start --extra-config "apiserver.cors-allowed-origins=["http://boot.dev"]"
minikube dashboard --port=63840
```

#### Deploy an image
```bash
kubectl create deployment synergychat-web --image=bootdotdev/synergychat-web:latest
kubectl get deployments
kubectl get pods
kubectl port-forward $PODNAME 8080:8080
```

#### Edit a deployment image
Allows you to edit the `yaml` file for the deployment
```bash
kubectl edit deployment synergychat-web
```

#### Use a proxy
```bash
kubectl get pods -o wide
kubectl proxy
http://127.0.0.1:8001/api/v1/namespaces/default/pods
```

### Deployments
```bash
kubectl get replicasets
kubectl get pods
kubectl get deployment synergychat-web -o yaml > web-deployment.yaml
# make changes, then apply them
kubectl apply -f web-deployment.yaml
```

### Services
```bash
kubectl apply -f web-service.yaml
kubectl port-forward service/web-service 8080:80
# svc is short for service
kubectl get svc web-service -o yaml
```

`ClusterIP` is the default service. There are other types of services like `NodePort` and `LoadBalancer`, etc.


