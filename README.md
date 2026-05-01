# EM DevOps Test Task
## Запуск
```bash
git clone https://github.com/hoolea/test_task_em.git && cd ./test_task_em
cp .env_example .env
docker compose up --build
```
или
```bash
git clone https://github.com/hoolea/test_task_em.git && cd ./test_task_em
cp .env_example .env
make up
```
## Проверка
```bash
curl http://localhost
```
Ожидаемый результат:
```bash
Hello from Effective Mobile!
```
## Архитектура
```
Client -> Nginx (port 80) -> Backend (port 8080)
```
+ Nginx принемает HTTP-запросы
+ Проксирует их на backend
+ Backend отвечает текстом
## Используемые технологии
+ Docker
+ Docker Compose
+ Nginx
+ Python (http.server)
## Особенности
+ Backend не доступен снаружи
+ Контейнеры общаются через Docker network
+ Backend работает не от root
+ Имеется проверка состояния контейнера (healthcheck)

  