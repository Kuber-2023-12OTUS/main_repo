Чтобы протестировать на minicube, нужно поставить метку на ноду для того, чтобы она удовлетворяла nodeselector:
```shell
kubectl label nodes minikube homework="true"
```