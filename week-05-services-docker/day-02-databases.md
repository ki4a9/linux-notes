Неделя 5 День 2  
Базы данных  
- PostgreSQL - одна из популярных систем управления базами данных, надежная и расширяемая.
  - sudo apt install postgresql postgresql-contrib -y - установка  

В PostgreSQL управление доступом основано на ролях. Роль с атрибутом LOGIN - это и есть пользователь.
По умолчанию в системе создается суперпользователь postgres, чтобы выполнить команды от его имены: sudo -u postgres.
  - sudo -u postgres createuser --interactive - создает новую роль и спрашивает будет ли она суперпользователем
- sudo -u postgres psql - попадаем в консоль postgres
  - ALTER USER admin WITH PASSWORD 'твой_надёжный_пароль'; - присваиваем нашей роли(суперюзера) новый пароль
- sudo -u postgres createdb -O admin mydb - создаем базы данных mydb и делаем admin владельцем
- psql -h localhost -U admin -d mydb - вход в нашу базу данных  

- sudo -u postgres psql - в консоли postgres можно проверить пользователей и базы данных
  - \du - список ролей
  - \l - список баз данных
  
все это можно делать и одной командой, но лучше я пока разберу по шагам  
Создание бэкапа(дампа) базы данных  
- pg_dump -U myuser -d mydb -f mydb_backup.sql - файл mydb_backup.sql будет содержать все sql-команды для восстановления базы
- sudo -u postgres createdb -O myuser new_mydb - перед восстановлением ОБЯЗАТЕЛЬНО создаем базу если ее нет совсем
- psql -U myuser -d new_mydb -f mydb_backup.sql - загружаем в нее данные(восстанавливаем)

 
