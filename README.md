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

![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/e6a5c5b0-20c3-4613-8fe6-a98871bc560d)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/cb30d3ef-1dfb-4b10-b808-aaca3b5c6eab)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/6520b392-6bb9-441e-a660-88dff9843b95)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/eeda2e8e-214c-4aa6-9a5c-42c99988d649)


Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.

Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/73eca8ae-134c-4b0d-8d62-47e9dda82785)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/5a26bd94-edc9-483d-a82b-022f45bd4e39)

![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/8a33d8c9-81af-450d-b01f-fa06a70ff364)



![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/9bba73c2-2b1f-4f20-b151-eb1b25fc2351)
![image](https://github.com/AlexanderSchelokov/Disaster-recovery-Keepalived-hw/assets/121572590/8aeb4105-f41b-43ca-a3aa-40a7dc03fda3)



На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html

