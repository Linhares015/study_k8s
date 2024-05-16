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

kubectl port-forward svc/postgres 5432:5432 -n dev-athena

kubectl create secret generic git-ssh-key   --from-file=id_ed25519=/home/linhares/.ssh/id_ed25519   --from-file=known_hosts=/home/linhares/.ssh/known_hosts -n dev-athena


 hop_ssh_connection

 kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml


docker volume create --name=postgres_data --opt type=tmpfs --opt device=tmpfs --opt o=size=10g


docker run -d \
  --name meu_postgres \
  -e POSTGRES_PASSWORD=minha_senha_secreta \
  -v postgres_data:/var/lib/postgresql/data \
  -p 5432:5432 \
  --restart always \
  postgres

docker run -d \
  --name meu_mysql \
  -e MYSQL_ROOT_PASSWORD=minha_senha_secreta \
  -v mysql_data:/var/lib/mysql \
  -p 3306:3306 \
  --restart always \
  mysql:latest

docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=SuaSenha@123' \
  -p 1433:1433 --name sqlserver \
  -d mcr.microsoft.com/mssql/server:2019-latest

minikube start --driver=docker --cpus=5 --memory=20096