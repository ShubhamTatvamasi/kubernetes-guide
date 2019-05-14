# GCP

First check the project you are in.

Get list of clusters on GCP
```
gcloud container clusters list
```

Get the cluster info from different project
```
gcloud container clusters get-credentials kubeflow-05-4
```

Create a new cluster on GCP
```
gcloud container clusters create kubernetes-course \
--zone us-central1-a \
--machine-type n1-standard-1 \
--disk-size 10 \
--disk-type pd-ssd \
--num-nodes 1 \
--min-nodes 1 \
--max-nodes 3
```

Add autoscaling flag laster on
```
--enable-autoscaling
```

Delete cluster on GCP
```
gcloud container clusters delete kubernetes-course \
--zone us-central1-a
```

Resizing a cluster
```
gcloud container clusters resize kubernetes-course \
--node-pool default-pool \
--num-nodes 1
```
