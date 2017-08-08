# Движок блога Эгея в Docker-контейнере.
### Связка Caddy + PHP7 + MySQL. https от Let's Encrypt из коробки.

1. Склонируйте на сервер или на свой компьютер этот репозиторий.

2. Скачайте архив с [последней версией Эгеи](http://blogengine.ru/get/).

3. Распакуйте содержимое архива в папку `blog` внутри текущего проекта.

4. В файле `docker-compose.yaml` пропишите желаемые логин, пароль и название базы данных.

5. Для развертывания Эгеи на компьютере разработчика в файле `caddy/Dockerfile` в 30 строке вставьте `COPY Caddyfile.dev /etc/Caddyfile`

6. Для развертывания Эгеи на боевом сервере измените название домена в файле `Caddyfile.prod` и в `caddy/Dockerfile` в 30 строке вставьте `COPY Caddyfile.prod /etc/Caddyfile`. В файле `docker-compose.yaml` в секции конфигурации caddy оставьте только 80 и 443 порты.

7. В  `blog/user/config.php` нужно прописать: `$_config['url_composition'] = 'synthetic';` и после этого сбросить кеш `/?go=@sync/`