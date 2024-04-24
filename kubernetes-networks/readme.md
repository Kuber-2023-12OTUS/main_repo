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

В ответ должна прийти html страница.

Установка ingress с помощью Helm - 
```shell
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install nginx-ingress ingress-nginx/ingress-nginx --create-namespace --namespace ingress-nginx
```

Узнать ip ingress 
```shell
kubectl -n homework get ing
```

Добавить в etc/hosts 
```shell
192.168.1.228     homework.otus
```
ip адрес нужно заменить на полученный в предыдущем шаге

Проверить доступность сайта:
```shell
curl http://homework.otus/
```



