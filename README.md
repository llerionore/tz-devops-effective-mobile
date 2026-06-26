# Effective Mobile Test Task
Тестовое веб-приложение с Python бэкендом и Nginx как реверс-прокси, все запущено в Docker 

## Стэк
- Python 3.13 (http.server)
- nginx 1.30.3-alpine
- Docker
- Docker Compose

## Процесс работы
Пользователь обращается на 80 порт, запрос идет к nginx. Nginx принимает запрос и перенаправляет его на бэкенд по имени сервиса внутри докер-сети. Наружу торчит только 80 порт Nginx, бэкенд снаружи недоступен. 

User -> nginx:80 -> backend:8080

## Запуск
```bash
docker compose up -d --build
```

## Проверка
```bash
curl http://localhost
```

Как результат, должно выйти:
"Hello from Effective Mobile!"

Или можно прописать в браузере http://localhost (без портов), на экране должна появиться та же надпись.

## Остановка
```bash
docker compose down
```
