Чтобы запустить проект в директории kubernetes-network выполняем команду
```shell
kubectl apply -f .
```

Чтобы протестировать svc, нужно сначала узнать ip адрес сервиса:
```shell
kubectl get services -n homework
```

Затем выполнить команду 

```shell
kubectl exec -ti homework-deployment-6685cd6dff-v7vnl -n homework -- curl http://10.105.45.150
```
Где нужно заменить имя пода и адрес, полученный выше