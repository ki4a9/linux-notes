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
