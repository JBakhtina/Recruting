Recruting
=========

Web application of recruitment web-portal with REST backend.




Recruting
=========

Система размещения вакансий

## Установка
1. Скачать этот проект
2. Создать область ```vacancy```, с новой БД и стандартным веб-приложением
3. Проверить веб приложение ```/csp/vacancy```
  - Name: /csp/vacancy
  - Namespace: vacancy
  - Allowed Authentication Methods: Unauthenticated
  - AllowedDispatch Class: WEB.Broker
  - Application Roles: %All
  - CSP Files Physical Path: проверить что он существует в ФС
4. Импортировать проект, скомпилировать
5. Создать веб приложение ```/v```
  - Name: /v
  - Namespace: vacancy
  - Allowed Authentication Methods: Unauthenticated
  - Dispatch Class: WEB.Broker
  - Application Roles: %All
6. Создать веб приложение ```/av```
  - Name: /av
  - Namespace: vacancy
  - Allowed Authentication Methods: Unauthenticated
  - Dispatch Class: WEB.AdminBroker
  - Application Roles: %All
7. Открыть ```http://localhost:57772/csp/vacancy/index.html``` должна
отобразиться шапка проекта
8. В терминале выполнить 

  ```
     zn "vacancy"
     set u=##class(Vacancy.SystemUser).%New()
     set u.FirstName="Admin"
     set u.Login="Admin"
     set u.Password=##class(WEB.JSON).MD5HEX("Password")
     w u.%Save()
  ```
9. Открыть ```http://localhost:57772/csp/vacancy/index.htm```
10. Авторизоваться с Admin/Password
11. Перейти в Личный кабинет ->  Настройки
12. Настроить там URL проекта и почту. Сохранить.
