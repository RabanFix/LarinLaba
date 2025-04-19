## Задание 7

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
   <p>Рисунок 5 - getenforce</p>
</div>

