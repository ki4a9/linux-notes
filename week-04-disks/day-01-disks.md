Неделя 4 День 1  
Управление дисками  

- lsblk - посмотреть все диски и разделы системы в виде дерева.
  - lsblk -f - показать файловую систему и UUID(уникальный идентификатор файловой системы)
  - lsblk /dev/sdb - только конкретный диск
- fdisk - инструмент для работы с таблицей разделов, разметка диска(MBR\GPT)
  - sudo fdisk /dev/sdb - работа с конкретным диском (введя эту команду мы попадем в интерактивный режим)
  - пример работы с диском:   
<img width="459" height="161" alt="image" src="https://github.com/user-attachments/assets/777c1bd6-da36-42d0-ad4d-e102cf54c400" />    
  
После не лишним будет перечитать изменения sudo partprobe /dev/sdb  
- mkfs - форматирование диска в нужную файловую систему.
  - sudo mkfs.ext4 /dev/sdb1 - форматирование в ext4
  - sudo mkfs.xfs /dev/sdb1
  - sudo mkfs.vfat /dev/sdb1 - в fat32 (для флешек) /а в ntfs можно?
  - sudo mkfs.ext4 -L MYDATA /dev/sdb1 - подписать диск(задать метку)
- mount - монтирует диски и каталоги к точку монтирования(выбранной папке в линукс)
  - sudo mount /dev/sdb1 /mnt/data - монтируем sdb1 в папку data
  - sudo mount -t ext4 /dev/sdb1 /mnt/data - указать тип при монтировании
  - sudo mount -o loop ubuntu.iso /mnt/iso - монтировать iso образ
  - mount - посмотреть все смонтированные файловые системы
  - sudo umount /mnt/data или - sudo umount /dev/sdb1 - размонтировать sdb1
- /etc/fstab - mount работает до перезагрузки, чтобы разделы автоматически монтировались во время загрузки системы их нужно прописать в fstab
   - <устройство>  <точка_монтирования>  <тип_ФС>  <опции>  <dump>  <pass>  - формат строки
   - UUID=abc123-def456  /mnt/data  ext4  defaults  0  2 - пример монтирования
   - sudo mount -a - проверить синтаксис файла на ошибки 
