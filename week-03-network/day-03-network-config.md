Неделя 3 День 3  
Настройка сети  

два подхода - классический и современный. файл /etc/network/interfaces и netplan.  

Классический(/etc/network/interfaces): этот метод я знаю достаточно хорошо, поэтому напишу на мой взгляд самые интересные строки конфигурации.    
- auto eth0 - имя интерфейса который нужно поднимать при старте системы
- allow-hotplug eth0 - поднимать интерфейс при обнаружении
- iface eth0 inet dhcp(static) - статические настройки или полученные от дхцп сервера.

применить настройки - sudo ifdown eth0 && sudo ifup eth0 ну или systemctl restart networking

Современный(netplan): читает yaml файл с конфигурацией из /etc/netplan и передает настройки либо systemd-network(обычно если это сервер) либо networkmanager(если это декстоп версия с гуи)  
файл конфигурации netplan очень чувствителен к отступам. вот пример файла для статических настроек:  

<img width="429" height="313" alt="image" src="https://github.com/user-attachments/assets/dd745856-fa39-4b8a-a9f6-a5ac50ec9d8c" /> 

применить настройки - sudo netplan apply


