# kubeflow

Downscale

```
gcloud container node-pools list --cluster kubeflow-05-4 --zone us-west1-b
```

```
gcloud container node-pools create kubeflow-05-4-cpu-pool-v2 --cluster kubeflow-05-4 --zone us-west1-b --machine-type n1-standard-4 --num-nodes=2
```

```
kubectl get nodes -l cloud.google.com/gke-nodepool=kubeflow-05-4-cpu-pool-v1
```

```
for node in $(kubectl get nodes -l cloud.google.com/gke-nodepool=kubeflow-05-4-cpu-pool-v1 -o=name); do
  kubectl cordon "$node";
done
```

```
for node in $(kubectl get nodes -l cloud.google.com/gke-nodepool=kubeflow-05-4-cpu-pool-v1 -o=name); do
  kubectl drain --force --ignore-daemonsets --delete-local-data --grace-period=10 "$node";
done
```

```
gcloud container node-pools delete kubeflow-05-4-cpu-pool-v1 --cluster kubeflow-05-4 --zone us-west1-b
```
