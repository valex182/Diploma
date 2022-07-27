# DiplomQA
## Инструкция по подключению БД, запуску SUT и авто-тестов
### 1. Склонировать проект
- репозиторий: https://github.com/Valex182/Diploma.git
- команда: `git clone`
### 2. Скачать и запустить в Docker контейнеры
- СУБД: MySQL (image mariadb), PostgreSQL; Node.js
- команда для запуска контейнеров: `docker-compose up`
### 3. Запустить SUT
-  команда для запуска с подключением MySQL: `java -Dspring.datasource.url=jdbc:mysql://localhost:3306/app -jar artifacts/aqa-shop.jar`
-  команда для запуска с подключением PostgreSQL: `java -Dspring.datasource.url=jdbc:postgresql://localhost:5432/app -jar artifacts/aqa-shop.jar`
-  приложение зпускается по адресу: http://localhost:8080/
### 4. Запустить авто-тесты
- команда для запуска с подключением MySQL: `./gradlew clean test -Ddb.url=jdbc:mysql://localhost:3306/app allureServe`
- команда для запуска с подключением PostgreSQL: `./gradlew clean test -Ddb.url=jdbc:postgresql://localhost:5432/app allureServe`
### 5. Сгенерировать отчеты Allure
- команды для генерации: `./gradlew allureReport` и `./gradlew allureServe`
- для завершения работы allureServe выполнить команду: `Control + С`