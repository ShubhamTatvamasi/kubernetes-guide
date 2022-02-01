# run

run commands on pods:
```bash
kubectl run nginx --image=nginx 

kubectl run busybox --generator=run-pod/v1 --image=busybox

kubectl run busybox --dry-run -o yaml --image=busybox -- sleep infinity 

kubectl run busybox --image=busybox -- sleep infinity
```

Install ansible on pod:
```bash
kubectl run ubuntu --image=ubuntu -- bash -c 'apt update; apt install ansible -y; ansible-galaxy collection install shubhamtatvamasi.magma'

kubectl create deployment ubuntu --image=ubuntu -- bash -c 'apt update; apt install ansible -y; ansible-galaxy collection install shubhamtatvamasi.magma'

kubectl scale deploy ubuntu --replicas=50
```

ansible test
```bash
kubectl create deployment ansible-test --image=shubhamtatvamasi/ansible:test
kubectl scale deploy ansible-test --replicas=50
```


