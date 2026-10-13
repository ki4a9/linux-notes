Неделя 5 День 3  
Файловый сервер  

- Samba - файловый сервер, реализующий SMB/CIFS для совместимости с windows
  - sudo apt install samba - установка для пакета для хостинга папок
  - sudo apt install cifs-utils - пакет для подключения к расшаренным папкам
- Расшарить папку на сервере()
  - sudo mkdir -p /srv/samba/shared - создаем папку, которую будем шарить
  - sudo chown nobody:nogroup /srv/samba/shared - задаем папке владельца
  - sudo chmod 777 /srv/samba/shared - права на каталог(полные для всех)
  - sudo nano /etc/samba/smb.conf
    
    <img width="301" height="184" alt="image" src="https://github.com/user-attachments/assets/1fc7ff87-29ad-4fb1-8dd9-6e2b07a0cc00" />

  - testparm - проверка конфига
  - sudo systemctl restart smbd - перезапуск самбы
  - sudo ufw allow samba - разрешение в файерволе
- Подключиться к папке
  - sudo mkdir -p /mnt/samba/shared - создать точку монтирования
  - sudo mount -t cifs //192.168.1.50/shared /mnt/samba/shared -o guest - гостевой доступ
- Пример подключения к виндовс шаре с линукс дебиан(fstab запись, протокол smb-1.0)
  - //10.42.99.8/Общая\040папка /mnt/winshare cifs username=user,password=password,vers=1.0,noperm 0 0 
  

