### IBM Cloud CLI

Get the list Kubernetest clusters
```bash
ibmcloud ks cluster ls
```

Get the details for a specfinc cluster
```bash
ibmcloud ks cluster get microservices
```
> `microservices` is the name of a cluster

Get the list of workers for a cluster
```bash
ibmcloud ks worker ls microservices
```
