Неделя 5 День 5  
Docker Compose  

- Docker Compose - позволяет описать все приложение(контейнеры, связи, тома, сети) в одном yml-файле и запустить одной командой
  - Структура файла yml - services(контейнеры), volumes(тома данных), networks(сети)
  - Для примера файл [docker-compose.yml](docker-compose.yml)
  - sudo mkdir -p home/kicha/docker-compose-lab - директория для проекта
  - sudo docker compose up -d - создать и запустить все сервисы в фоне(нужно быть в каталоге с yml)

- несколько базовых команд
  <img width="831" height="354" alt="image" src="https://github.com/user-attachments/assets/f87d9e89-a935-4316-865b-862231b9bc08" />
