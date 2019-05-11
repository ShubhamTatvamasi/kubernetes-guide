# kubernetes-course


Check if the cluster is running
```
kubectl get node
```

For deploying the pod
```
kubectl apply -k base
```

For deleting the pod
```
kubectl delete -k base
```

Get the list of all deployments
```
kubectl get deployments
```

Get the list of one deployment
```
kubectl get deployments hello
```

Get the detailed description of deployment
```
kubectl describe deployments hello
```

For getting list of all pods
```
kubectl get pods
```

For getting inside pod
```
kubectl exec -it hello-75b944d997-6pqd4 -- sh
```

For getting list of all services
```
kubectl get service
```

Get the detailed description of service
```
kubectl describe service hello
```

Update node role to master
```
kubectl label node docker-for-desktop node-role.kubernetes.io/master=master
```

---
Docker Compose
```
docker-compose up -d
```
