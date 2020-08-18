# Deploy
kubectl apply -f config.yaml -f postgres-1.yaml -f initdb-1.yaml -f postgres-2.yaml -f initdb-2.yaml -f postgres-3.yaml -f initdb-3.yaml -f deployment.yaml -f service.yaml -f ingress.yaml

## Описание архитектурного решения
Key Based Sharding (hash based).<br>
Routing: из приложения (умный клиент).<br>
Ключ хэширование - артикул (vendorCode).<br>
Функция хэширования - остаток от деления на кол-во баз (3).<br>
Проблем с неравномерным распределением не должно быть.
