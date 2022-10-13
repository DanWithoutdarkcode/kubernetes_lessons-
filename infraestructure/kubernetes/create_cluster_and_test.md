# Comandos principales

## Link de resources "kind"

Lectura https://kind.sigs.k8s.io/docs/user/quick-start/

## Comandos para arrancar cluster de jubernetes


kind create cluster --name cluster-apps --config cluster.yaml

## Con este comando eliminamos todo nuestro cluster
kind delete cluster --name cluster-apps

## Desplegamos ingress controller en nuestro cluster

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

## Desplegamos loadbalancer metallb

kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.13.5/config/manifests/metallb-native.yaml

------------------------------------------


## Deploy hello world

kubectl apply -f test/wdc-test-service.yaml

## Ver servicios

kubectl get services

## Revsiar objetos creados

kubectl get all,cm,secret,ing -A

# Test

curl [IP cluster]/wdc

curl 192.168.137.129/wdc


# Remover objetos


kubectl delete -f wdc-test-service.yaml

kubectl delete -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

kubectl delete -A ValidatingWebhookConfiguration ingress-nginx-admission


## Revsiar objetos creados

kubectl get all,cm,secret,ing -A