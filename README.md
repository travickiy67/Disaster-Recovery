# Травицкий Сергей
# Домашнее задание к занятию «Disaster Recovery. FHRP и Keepalived».  

### Задание 1
- Дана [схема](https://github.com/netology-code/sflt-homeworks/tree/main/1/hsrp_advanced.pkt) для Cisco Packet Tracer, рассматриваемая в лекции.
- На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
- Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
- Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
- На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.

---
### Решение 1
[Cхемa](https://github.com/travickiy67/Disaster-Recovery/raw/refs/heads/main/files/HSRP.pkt) файл HSRP.pkt.  

### Скрины наcтройки

**Cкрин 1**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img01.png)   

Понижение приоритета при потере линка на первом роутере.  

**Скрин 2**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img02.png)  

**Скрин 3**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img03.png)  

Приоритета при потере линка на втором роутере  

**Скрин 4**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img04.png)  

---
### Задание 2
- Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного [файла](https://github.com/netology-code/sflt-homeworks/blob/main/1/keepalived-simple.conf).
- Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
- Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
- Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
- На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html

---

**Файл keepalived.conf**
[файл](https://github.com/travickiy67/Disaster-Recovery/blob/main/files/keepalived.conf)  

**Файл keepalived.sh**
[файл](https://github.com/travickiy67/Disaster-Recovery/blob/main/files/keepalived.sh)  
**Скрин 1**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img1.1.png)  

**Скрин 2**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img1.2.png)  
а
**Скрин 3**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img1.3.png)  

**Скрин 4**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img1.4.png)  

**Скрин 5**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img1.5.png)  

**Скрин 6**  
![alt text](https://github.com/travickiy67/Disaster-Recovery/blob/main/img/img1.6.png)  
