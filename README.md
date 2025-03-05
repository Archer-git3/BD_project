# DB project

Github repository for doing labs on the subject "Databases". 

Option conditions for the 1st laboratory:

`2. Порівняти середній бал з 
Української мови та літератури у кожному регіоні
у 2020 та 2019 роках серед тих кому було зараховано тест`

# Инструкция по запуску программы:

После загрузки кода с репозитория на локальный компьютер, убедитесь что приложение Docker запушено.
1. Введите команду `docker-compose build` для создания образа, согласно правилам описанным в проекте.
2. Введите команду `docker-compose up -d` для создания и запуска контейнеров базы данных, pyhton приложения app и браузерного клиента PgAdmin4. Рекомендую использовать флаг `-d` для работы в фоновом режиме, чтоюы не получать сообщения вывода в консоль. 
3. После запуска контейнеров, база данных будет создана и включена, а приложение начнет свою работу, логируя все стадии программы. Вы можете посмотреть на вывод контейнера через приложение Docker или команду в терминале.

Контейнер PgAdmin4 позволяет подключиться к базе данных через браузерный клиент по адресу `localhost/browser`. Для подключения используйте данные из файла переменных окружения `.env`

После того, как приложение закончит свою работу, оно выдаст время своей работы и создаст csv файл с результом запроса, указанного в варианте. 

# Результаты и логирование
### Файл з результатами виконання запиту та легенду до нього.

По умолчанию файл с результатом называется `result_variant_2.csv` и создается по пути `./app/data`. Данная папка так же является томом(volume), так что после окончания работы приложения в контейнере она обновляется на вашей операционной системе. 

Копию данного файла прилагаю в корневую папку проекта, для проверки результатов без запуска программы. 

### Файл з вимірами часу роботи завантаження даних у БД

Файлы с логированием и измерением времени лежат по пути `./logging/`. 

Всего присутсвуют 3 файла.

Для нормальной ситуации:
- `app_logging_normal.txt` 

Для ситуации с падением базы данных:
- `app_logging_with_crashing.txt`
- `db_logging_with_crashing.txt`
