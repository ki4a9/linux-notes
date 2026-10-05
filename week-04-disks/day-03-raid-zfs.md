Неделя 4 День 3  
RAID  

- mdadm - утилита для создания и мониторинга программных raid массивов.
  - перед тем как создавать рэйд массив, нужно разметить диски(задать им соответствующий типа раздела - fd)
    - sudo fdisk /dev/sdb - заходим в настройку нужного нам диска
    - n → p → 1 → Enter → Enter → t → fd → w - в интерактивном режиме настраиваем его
  -  создание рэйда 1:
    <img width="372" height="153" alt="image" src="https://github.com/user-attachments/assets/af42d268-7b4c-433a-b412-8a17b2b847ae" />  

  - cat /proc/mdstat - проверка состояния массивов
  -  sudo mdadm --detail /dev/md0 - это тоже проверка, только подробная и конкретного
  -  Созданный массив можно использовать как обычный диск
  -  sudo mdadm --detail --scan | sudo tee -a /etc/mdadm/mdadm.conf - сохранение конфигурации массива, чтобы он собирался при загрузке системы
  -  sudo update-initramfs -u  - обновление файловой системы, чтобы увидеть наш рэйд
  -  sudo mdadm --remove /dev/md0 /dev/sdc - удалить диск(сбойный)
  -  sudo mdadm --add /dev/md0 /dev/sdc - добавить новый(вернуть старый)
  -  sudo mdadm --stop /dev/md0 - остановить массив
  -  sudo mdadm --assemble /dev/md0 - собрать обратно
    
  
