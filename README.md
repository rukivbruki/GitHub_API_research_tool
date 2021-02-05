**ЗАПУСК КОНТЕЙНЕРИЗОВАННОГО ПРИЛОЖЕНИЯ:**

_Консольная утилита:_

1. Клонируйте репозиторий,
2. Получите access token на платформе gitHub (https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token),
3. Добавьте в корень папки backend файл .env и пропишите туда директиву TOKEN = your_token,
4. Создайте и запустите контейнер приложения (не закрывайте вкладку):

- `docker-compose build`
- `docker-compose up`

5. В новой вкладке из директории с проектом выполните команду `docker ps` и скопируйте ID
 запущенного контейнер (container_ID),
6. Выполните команду `docker exec -it container_ID /bin/bash`,
7. выполните команду `npm run crawler`.

 **Примечание: для успешного сохранения данных на локальной машине необходимо дать Docker права на папку, в которую MongoDB сохраняет данные. В нашем случае это: /usr/local/var/mongodb**

_Веб клиент:_

1. Выполните действия 1-3 из инструкции по запуску консольного приложения?
2. Перейдите по адресу http://localhost:8080/ и при помощи веб интерфейса выполнить запуск приложения.

**ЗАПУСК ЛОКАЛЬНОГО ПРИЛОЖЕНИЯ**

_Консольная утилита:_

1. Установите в систему менеджер пакетов npm, программную платформу Node.js и базу данных MongoDB,
2. Запустите MongoDB,
3. Выполните шаги 1-3 из инструкции для запуска контейнеризованного приложения,
4. Из папки backend выполните команду node service/service --crawler (вторым параметром можно указать уровень логирования, например, DEBUG или ERROR),

_Веб клиент:_

1. Установите в систему менеджер пакетов npm, программную платформу Node.js и базу данных MongoDB,
2. Запустите MongoDB,
3. Выполните шаги 1-3 из инструкции для запуска контейнеризованного приложения,
4. Из папки backend выполните команду node service/service --server (вторым параметром можно указать уровень логирования, например, DEBUG или ERROR),
5. Из папки frontend выполните команду npm run serve,
6. Перейдите по адресу http://localhost:8080/ и при помощи веб интерфейса выполнить запуск приложения.