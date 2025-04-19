![image](https://github.com/user-attachments/assets/3c504660-36c5-4efe-a5b7-d0556676ad69)## Задание 7

Скачал вторую ВМ (назвал никнейм пользователя: rabanfix), установил гостевые дополнения и `wget`, `curl` и `git` (рис. 1).

<div align="center">
   <img src="https://github.com/user-attachments/assets/d855e538-602e-4c51-8214-d5c2d0db78b1" alt="" width="1000">
   <p>Рисунок 1 - Вторая ВМ</p>
</div>

Проверил включён ли фаерволл командой `sudo firewall-cmd --state` (рис. 2).

<div align="center">
   <img src="https://github.com/user-attachments/assets/d855e538-602e-4c51-8214-d5c2d0db78b1" alt="" width="1000">
   <p>Рисунок 2 - Фаерволл</p>
</div>

Написал команду (рис. 3):

```
sudo yum install wget tar
```

- Она послужит нам для работы с архивами.

<div align="center">
   <img src="https://github.com/user-attachments/assets/c33fd589-88ef-4027-bf34-6170dedf4fd9" alt="" width="1000">
   <p>Рисунок 3 - tar</p>
</div>

Написал команду (рис. 4):

```
sudo yum install chrony
```

- Данная команда нужна для синхронизации времени

<div align="center">
   <img src="https://github.com/user-attachments/assets/76590126-9525-41cf-80ec-8e4c4756e2d9" alt="" width="1000">
   <p>Рисунок 4 - chrony</p>
</div>

Написал команды (рис. 5):

```
systemctl enable chronyd
```

- Данная команда включает chrony

```
systemctl start chronyd
```

- Данная команду запускает chrony.

<div align="center">
   <img src="https://github.com/user-attachments/assets/6f91bec2-31be-406a-a936-6d2b6c8ef3e0" alt="" width="1000">
   <p>Рисунок 5 - Команды для включения и запуска</p>
</div>

При вводе команды `getenforce` получил ответ: `Enforcing`. Поэтому пришлось использовать следующие команды для отключения гетинфорс (рис. 6):

```
sudo setenforce 0
```

```
sudo sed -i 's/^SELINUX=.*/SELINUX=disabled/g' /etc/selinux/config
```

<div align="center">
   <img src="https://github.com/user-attachments/assets/c8851d4d-050e-45fd-ad7f-735ee190d037" alt="" width="1000">
   <p>Рисунок 6 - getenforce</p>
</div>

Скачал Prometheus. 3.3.0 / 2025-04-15 версией командой (рис. 7):

```
wget https://github.com/prometheus/prometheus/releases/download/v3.3.0/prometheus-3.3.0.linux-amd64.tar.gz
```

<div align="center">
   <img src="https://github.com/user-attachments/assets/39637682-fd90-4195-b24d-51bba1fe2a67" alt="" width="1000">
   <p>Рисунок 7 - Prometheus. 3.3.0</p>
</div>

Создал директории для Prometheus (рис. 8) командой `sudo mkdir -p /etc/prometheus /var/lib/prometheus`.

<div align="center">
   <img src="https://github.com/user-attachments/assets/61a7f017-64f8-4bee-b1a2-b9431211cdee" alt="" width="1000">
   <p>Рисунок 8 - Директории</p>
</div>

Разархивировал файл командой `tar -zxf prometheus-*.linux-amd64.tar.gz` и перешёл в папку prometheus-*.linux-amd64 командой `cd prometheus-*.linux-amd64` (рис. 9).

<div align="center">
   <img src="https://github.com/user-attachments/assets/b95a0d5d-2238-439b-a8dd-a989281700d9" alt="" width="1000">
   <p>Рисунок 9 - Файл</p>
</div>

Выполнил команду `pwd` для проверки корректности папки (рис. 10).

<div align="center">
   <img src="https://github.com/user-attachments/assets/b6a6e084-867c-4ca3-acab-a07ffec783be" alt="" width="1000">
   <p>Рисунок 10 - Полный путь</p>
</div>

