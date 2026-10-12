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


 
