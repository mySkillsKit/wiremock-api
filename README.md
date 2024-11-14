## Вариант 1
### 1 Собираем образ wiremock
```shell
docker build -t wiremock-server .
```
### 2A Запускаем контейнер с маппингом на порт 8012
```shell
docker run -d -p 8012:8080 wiremock-server --verbose
```
### 2B Запукаем WireMock с поддержкой шаблонов:
```shell
docker run -d -p 8012:8080 wiremock-server --verbose --global-response-templating
```

## Вариант 2
### Или напрямую запуск wiremock без Dockerfile (если маппинги находятся в текущей директории):
```shell
docker run -d -p 8012:8080 -v $(pwd)/mappings:/home/wiremock/mappings wiremock/wiremock:2.32.0 --verbose --global-response-templating
```