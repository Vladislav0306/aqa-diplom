# Документация
[План тестирования](https://github.com/Vladislav0306/aqa-diplom/blob/master/documentation/Plan.md)

[Отчёт по итогам тестирования](https://github.com/Vladislav0306/aqa-diplom/blob/master/documentation/Report.md)

[Отчёт по итогам автоматизации](https://github.com/Vladislav0306/aqa-diplom/blob/master/documentation/Summary.md)

# Задача:
Автоматизировать сценарии комплексного сервиса, взаимодействующего с СУБД и API Банка.
Приложение представляет из себя веб-сервис.

![](https://github.com/Vladislav0306/aqa-diplom/blob/master/documentation/service.png)

Приложение предлагает купить тур по определённой цене с помощью двух способов:

1. Обычная оплата по дебетовой карте
1. Уникальная технология: выдача кредита по данным банковской карты


# Инструкция подключения БД и запуска SUT
1. Склонировать проект из репозитория командой ``` git clone ```
1. Открыть склонированный проект в Intellij IDEA
1. Для запуска контейнеров с PostgreSQL и Node.js использовать команду ``` docker-compose up -d --force-recreate --build ```
1. Запуск SUT
- для PostgreSQL ввести в терминале команду

``` java -jar artifacts/aqa-shop.jar -Dspring.datasource.url=jdbc:postgresql://localhost:5432/app ```

5. Запуск тестов (Allure)
- для запуска на PostgreSQL ввести команду

``` gradlew clean test -Ddb.url=jdbc:postgresql://localhost:5432/app allureReport ```

6. Открыть в Google Chrome ссылку http://localhost:8080
7. Для получения отчета Allure ввести команду ``` gradlew allureReport ```
8. После окончания тестов завершить работу приложения (Ctrl+C), остановить контейнеры командой ``` docker-compose down ```
