# k8s_config

## Prerequisites
- Minikube (Docker driver)
- Helm
- kubectl

1. **Start Minikube**:
   ```bash
   minikube start --driver=docker
   ```


2. **Install NFS Server & Provisioner**:

```bash
$ helm repo add nfs-ganesha-server-and-external-provisioner https://kubernetes-sigs.github.io/nfs-ganesha-server-and-external-provisioner/
$ helm install my-release nfs-ganesha-server-and-external-provisioner/nfs-server-provisioner
```


3. **Deploy**:

```bash
# Do it in this order!
kubectl apply -f pvc.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f job.yaml
```

4. **Test**:
   
```bash
minikube service nginx-service --url
```

Copy the IP address and use browser or cURL.