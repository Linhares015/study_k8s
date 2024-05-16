helm repo add airbyte https://airbytehq.github.io/helm-charts
helm repo update

helm install airbyte airbyte/airbyte -f values.yaml -n dev-athena
