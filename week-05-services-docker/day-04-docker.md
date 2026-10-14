Неделя 5 День 4  
Docker  

- Docker - это инструмент, который упаковывает приложение со всем его окружением в изолированный контейнер.
  - Установка
    - sudo apt install -y ca-certificates curl gnupg lsb-release - установка зависимостей
    - sudo mkdir -p /etc/apt/keyrings - директория для gpg ключа
    - curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg - скачиваем и добавляем gpg ключ
    - sudo nano /etc/apt/sources.list.d/docker.list - файл с репозиториями докера
    - deb [arch=amd64 signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu resolute stable - сам репозиторий
    - sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin - установка движка докера, клиента командной строки и плагина docker compose
    - sudo docker run hello-world - проверка корректности установки
  - запуск nginx в контейнере
    - docker run --name my-nginx -p 8080:80 -d nginx - (-p 8080:80 это проброс портов, порт 8080 на виртуалке будет перенаправлен в на порт 80 внутри контейнера, -d запуск контейнера в фоновом режиме)
  - просмотр логов
    - docker logs -f my-nginx - все логи в реальном времени
  - Volumes(тома), хранилища данных, которые живут отдельно от контейнера
    - sudo mkdir -p /home/kicha/my-nginx-site - папка, где будут лежать тома
    - sudo echo "\<h1>Привет из Docker Volume!\</h1>" > /home/kicha/my-nginx-site/index.html - в файл index.html запишем эту строку
    - sudo docker run --name my-nginx-v -p 8081:80 -v ~/my-nginx-site:/usr/share/nginx/html -d nginx - запустим контейнер, примонтировав эту папку
    - sudo docker volume ls - список всех томов
  - Сети для связи между контейнерами
    - sudo docker network create my-app-net - создать сеть
    - sudo docker run --name db --network my-app-net -d nginx - теперь при запуске контейнера мы сможем подключать свою сеть(--network my-app-net) и все контейнеры у которых будет эта сеть указанна будут "видеть" друг друга
    - sudo docker network ls - список сетей
    - sudo docker network inspect my-app-net - детали сети
- базовый набор команд
  
<img width="805" height="433" alt="image" src="https://github.com/user-attachments/assets/f1c3e3e5-82be-438f-a68c-c91301d6cacd" />

      
