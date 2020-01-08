### get inside kube-system pods

```bash
kubectl exec -it -n kube-system etcd-minikube -- sh
kubectl exec -it --namespace kube-system etcd-minikube -- sh
```
