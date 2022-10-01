# Comandos principales

## Link de resources "kind"

Lectura https://kind.sigs.k8s.io/docs/user/quick-start/

## Comandos para arrancar cluster de jubernetes


kind create cluster --name cluster-apps --config /opt/kubernetes/cluster/cluster.yaml

## Con este comando eliminamos todo nuestro cluster
kind delete cluster --name cluster-apps