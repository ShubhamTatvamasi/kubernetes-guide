# ibm cloud k8s

get vpn file
```bash
kubectl get secret vpn-config -n kube-system -o json | jq -r '.data["worker.ovpn"]' | base64 -d > worker.ovpn
```
