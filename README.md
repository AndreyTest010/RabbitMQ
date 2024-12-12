# Домашнее задание к занятию "`RabbitMQ`" - `Корнилов Андрей`



### Задание 1. Установка RabbitMQ
Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ. Добавьте management plug-in и зайдите в веб-интерфейс.

Итогом выполнения домашнего задания будет приложенный скриншот веб-интерфейса RabbitMQ.




![rabbit1](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit1.jpg)


---

### Задание 2. Отправка и получение сообщений
Используя приложенные скрипты, проведите тестовую отправку и получение сообщения. Для отправки сообщений необходимо запустить скрипт producer.py.

Для работы скриптов вам необходимо установить Python версии 3 и библиотеку Pika. Также в скриптах нужно указать IP-адрес машины, на которой запущен RabbitMQ, заменив localhost на нужный IP.

$ pip install pika
Зайдите в веб-интерфейс, найдите очередь под названием hello и сделайте скриншот. После чего запустите второй скрипт consumer.py и сделайте скриншот результата выполнения скрипта

В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения.



![rabbit2](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit2.jpg)
![rabbit3](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit3.jpg)


---

### Задание 3

Задание 3. Подготовка HA кластера
Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.

Пример содержимого hosts файла:

$ cat /etc/hosts
192.168.0.10 rmq01
192.168.0.11 rmq02
После этого ваши машины могут пинговаться по имени.

Затем объедините две машины в кластер и создайте политику ha-all на все очереди.

В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.

![rabbit4](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit4.jpg)
![rabbit7](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit7.jpg)

Также приложите вывод команды с двух нод:

$ rabbitmqctl cluster_status

![rabbit5](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit5.jpg)
![rabbit6](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit6.jpg)
Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:

$ rabbitmqadmin get queue='hello'

![rabbit8](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit8.jpg)
После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте параметры подключения в скрипте consumer.py на вторую ноду и запустите его.

Приложите скриншот результата работы второго скрипта.

![rabbit9](https://github.com/AndreyTest010/RabbitMQ/blob/main/rabbit9.jpg)

