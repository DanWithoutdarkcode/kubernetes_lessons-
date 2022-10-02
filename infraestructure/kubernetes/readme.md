# Comandos principales

## Link de resources "kind"

Lectura https://kind.sigs.k8s.io/docs/user/quick-start/

## Comandos para arrancar cluster de jubernetes


kind create cluster --name cluster-apps --config /opt/kubernetes/cluster/cluster.yaml

## Con este comando eliminamos todo nuestro cluster
kind delete cluster --name cluster-apps

## Desplegamos el ingress controller en nuestro cluster

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

## Deploy hello world


kubectl apply -f baeldung-service.yaml

## Ver servicios

kubectl get services

# Test

curl [IP cluster]/baeldung

curl 192.168.137.129/baeldung
