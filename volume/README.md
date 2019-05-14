# deploy Persistent Volumes

Create data disk
```
gcloud compute disks create \ 
--size=10GB \ 
--zone=us-central1-a \ 
my-data-disk
```

Create Persistent Volumes:
```
kubectl apply -f pvc-demo.yaml
```

Delete Persistent Volumes:
```
kubectl delete -f pvc-demo.yaml
```

See the disk description
```
gcloud compute disks describe gke-kubernetes-course--pvc-9c7925fa-7669-11e9-9f11-42010a8001d1 --zone us-central1-a
```
