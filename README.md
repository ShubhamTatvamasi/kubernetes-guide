# kubernetes-course

Get list of all the things running on cluster
```
kubectl get all
```

delete everything from a namespace
```
kubectl delete all --all
```
> `-n default`

delete crashed pods
```bash
kubectl delete pods --field-selector 'status.phase=Failed'
```

set namespace for current context
```bash
kubectl config set-context --current --namespace default
```

delete namespace which is stuck at `Terminating` state:
```bash
NAMESPACE=kubevirt
kubectl get namespace $NAMESPACE -o json > $NAMESPACE.json
sed -i -e 's/"kubernetes"//' $NAMESPACE.json
kubectl replace --raw "/api/v1/namespaces/$NAMESPACE/finalize" -f ./$NAMESPACE.json
```

Use the following flag for running process in background
```
--wait=false
```
---

Cluster Info
```
kubectl cluster-info
```

### namespaces

Get everything from all namespaces
```
kubectl get all --all-namespaces
```

list all namespaces
```
kubectl get namespace
```
---

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

Get inside a specfic container of a pod
```
kubectl exec -it kube-dns-b46cc9485-dvgrc -n kube-system -c kubedns -- sh
```
> use container name

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

Port forward on remote pod to local
```
kubectl port-forward $POD_NAME 8080:80
kubectl port-forward hello-deployment-7b75d99cb9-q7h5p 8080:80
```

Rollout 1 previous version
```
kubectl rollout undo deploy webapp
```

---
Docker Compose
```
docker-compose up -d
```
