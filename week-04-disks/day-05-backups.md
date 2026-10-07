Неделя 4 День 5  
Бэкапы  

- tar - Инструмент для создания архивов в Linux.
  - tar -cvf archive.tar /home/kicha/docs/ - создать архив
  - tar -xvf archive.tar - распаковать архив
  - tar -tvf archive.tar - посмотреть содержимое без распаковки
  - tar -czvf backup.tar.gz /home/kicha/docs/ - создать сжатый архив gzip
  - tar -cJvf backup.tar.xz /home/kicha/docs/ - создать сжатый архив xz(еще более сжатый)
  - tar -xzvf backup.tar.gz -C /tmp/restore/ - распаковка в нужный каталог
  - tar -czvf backup.tar.gz /etc /home /var/www - архив из нескольких каталогов
  - tar -czvf /backup/home-$(date +%Y-%m-%d).tar.gz /home/kicha/ - архив с датой в имени(бэкап почти)
- gzip, bzip2, xz - сжимают отдельные файлы, используются вместе с tar(умеет их вызывать через -z,-j,-J)
  - gzip file.txt - создаст file.txt.gz и УДАЛИТ оригинал, чтобы сохранить оригинал использовать флаг -k
  - gzip -d file.txt.gz - распаковка
  - gzip -9 file.txt - задать уровень сжатия (9 максимальный, 1 минимальный)
  - bzip2 -k file.txt - сжать и сохранить оригинал(среднее сжатие, средняя скорость)
  - xz -k -9 file.txt - максимально сжать и сохранить оригинал(самое сильное сжатие, самый медленный)
- zip - для совместимости с windows
   
  <img width="385" height="115" alt="image" src="https://github.com/user-attachments/assets/7b2be0ea-6c26-4b42-a210-f58a1d8a302e" />

- rsync - синхронизация файлов, умеет копировать только изменения в файлах
  - rsync -av источник назначение - базовый синтаксис
  - rsync -avh /home/kicha/docs/ /backup/docs/ - локальный бэкап
  - rsync -avzhP /home/kicha/docs/ user@server:/backup/docs/ - бекап по ssh
