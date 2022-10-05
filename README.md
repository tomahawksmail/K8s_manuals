# K8s_manuals
Вывести список нод в кластере:
```sh
kubectl get nodes
```

Вывести рессурсы в кластере:
```sh
kubectl get all
```

Чтобы получить исчерпывающую информацию об отдельном pod-е (или любом другом ресурсе):
```sh
kubectl describe pod/name
```

Чтобы просмотреть все активные развертывания в вашем текущем пространстве имен:
```sh
kubectl get deployments
```

Для более подробной информации об этом конкретном развертывании используйте такую команду (demo - имя PODa):
```sh
kubectl describe deployments/demo
```

Проверим, что POD (demo) запущен:
```sh
kubectl get pods --selector app=demo
```

Остановить конкретный Pod-объект:
```sh
kubectl delete pods --selector app=demo
```

Остановить deployment:
```sh
kubectl delete all --selector app=demo
```

Передавать YAML-манифесты кластеру, используя команду kubectl apply:
```sh
kubectl apply -f k8s/deployment.yaml
```

Удалить все ресурсы, описанные в файлах манифестов:
```sh
kubectl apply -f k8s/deployment.yaml
```

Установка приложения при помощи HELM [a link](install - https://helm.sh/docs/intro/install/):
```sh
helm install --name demo ./k8s/demo
```

Чтобы проверить, какие выпуски запущены на данный момент:
```sh
helm list
```

Чтобы вывести состояние конкретного release:
```sh
helm status
```

Создать пространство имен demo и запустить манифест:
```sh
kubectl create namespace demo
kubectl apply --namespace demo -f k8s/resourcequota.yaml
```

Чтобы проверить, активирован ли ресурс ResourceQuotas в конкретном пространстве имен, используйте команду:
```sh
kubectl get resourcequotas
```
