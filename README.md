Задание 1
Дана схема для Cisco Packet Tracer, рассматриваемая в лекции.
На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/436fe587-a5f1-49f0-a3a2-d2eba3ce8b84)

Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/e18022e0-8e7b-4a74-9861-4f46013f6eb8)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/2ac409b0-0fa2-41dd-88e6-ede4f76ede87)

Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/5071c2e0-205b-43c9-b9b3-1fb700edca6e)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/0a8f844c-7ee5-4ecb-a936-da5516e01641)

После восстановления линии
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/3d5566ac-2c27-447c-9403-8dfb6fdeb826)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/0242cd40-5d7e-4d95-95fb-c16e5057d89b)


На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.


Задание 2
Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного файла.
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/4604fbe8-cbae-48cb-9aa3-26397b671397)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/37321972-bdd9-49d4-93f2-aa64cf23794f)

Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах

![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/8b14ef47-9f4a-47c8-ba9f-86a6cc1a3211)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/b2956d71-23ba-4f02-a21d-0f861a47dc63)

![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/cb30d3ef-1dfb-4b10-b808-aaca3b5c6eab)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/6520b392-6bb9-441e-a660-88dff9843b95)



Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.

Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/5642d56a-525a-48e4-949c-67449bbbdca8)


На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/fe90e3b2-6c4d-4ec0-a82d-c0b7ae9d8831)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/aa7fbafa-3858-49b2-a598-fce9e8972c6f)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/18500ba5-5a4e-4ed1-a18b-8aab2778695b)

