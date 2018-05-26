# Как это развернуть

1. Скачиваем подмодули
``` bash
$ git submodule update --init --recursive
```

2. Применяем заплатку для docker-1c-server
``` bash
$ cd docker-1c-server && git apply ../docker-1c-server.patch
```

3. Скачиваем необходимые файлы 1C сервера и кладём их в папку docker-1c-server

4. Заменяем аргументы `PLATFORM_VERSION`, `SERVER_VERSION` и идентификатор docker образа `docker-compose.yml`, на те которые скачали на предыдущем шаге

5. Правим настройки сети, если это необходимо 

6. Запускаем
``` bash
# docker-compose up -d
```

# Баги

1. Postgres не проверяет пароль (см. https://github.com/alexanderfefelov/docker-postgrespro-1c/issues/2)
