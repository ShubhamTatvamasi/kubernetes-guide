# Migrating workloads to different machine types


See the list of node pool
```
gcloud container node-pools list --cluster kubernetes-course --zone us-central1-a
```

Create new node pool with high config
```
gcloud container node-pools create larger-pool --cluster kubernetes-course --zone us-central1-a --machine-type n1-standard-2 --num-nodes=1 --disk-size 20 --disk-type pd-ssd
```

See current pod which node are they using
```
kubectl get pods -o=wide
```

Cordon the existing node pool:
```
for node in $(kubectl get nodes -l cloud.google.com/gke-nodepool=default-pool -o=name); do
  kubectl cordon "$node";
done
```

Drain the existing node pool:
```
for node in $(kubectl get nodes -l cloud.google.com/gke-nodepool=default-pool -o=name); do
  kubectl drain --force --ignore-daemonsets --delete-local-data --grace-period=10 "$node";
done
```

Delete old node pool:
```
gcloud container node-pools delete default-pool --cluster kubernetes-course --zone us-central1-a
```
