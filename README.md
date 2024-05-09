# study_k8s

Aprendendo Kubernetes

## Comandos

### Minikube

```bash
minikube start
minikube status
minikube stop
minikube delete
```

### Kubectl

```bash
kubectl get nodes
kubectl get pods
kubectl get services
kubectl get deployments
kubectl get replicaset
kubectl get all
kubectl describe pod <pod-name>
kubectl describe service <service-name>
kubectl describe deployment <deployment-name>
kubectl describe replicaset <replicaset-name>
kubectl describe node <node-name>
kubectl logs <pod-name>
kubectl exec -it <pod-name> -- /bin/bash
kubectl apply -f <file-name>
kubectl delete -f <file-name>
kubectl delete pod <pod-name>
kubectl delete service <service-name>
kubectl delete deployment <deployment-name>
kubectl delete replicaset <replicaset-name>
kubectl delete node <node-name>
```

### Docker

```bash
docker build -t <image-name> .
docker run -p 8080:8080 <image-name>
docker ps
docker stop <container-id>
docker rm <container-id>
docker rmi <image-name>
```

### Helm

```bash
helm install <release-name> <chart-name>
helm list
helm status <release-name>
helm uninstall <release-name>
```


curl http://localhost:8080
kubectl port-forward svc/airflow-web 8080:8080 -n dev-athena
