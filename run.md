
```bash

kubectl run nginx --image=nginx 

kubectl run busybox --generator=run-pod/v1 --image=busybox

kubectl run busybox --dry-run -o yaml --image=busybox -- sleep infinity 

kubectl run busybox --image=busybox -- sleep infinity
```
