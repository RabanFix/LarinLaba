![image](https://github.com/user-attachments/assets/c11f0205-a5d4-46fb-bd9c-6487058be89b)# Laba
## Задание 1 ##
Была прописана команда `sudo yam istall wget`, после чего была получена ошибка `is not a sudoers file`.

Для этого, сначала заходим под супер пользователя командой `su` (рис. 1).

<div align="center">
   <img src="https://github.com/user-attachments/assets/c363c8b5-4aee-4d9b-a664-0fcc9f36602e" alt="" width="500">
   <p>Рисунок1 - Супер пользователь</p>
</div>

Данная ошибка решается путём команды `sudo vi /etc/sudoers`, которая открывает конфигурационный файл, и была добавлена следующая строчка `Larin  ALL=(ALL)  ALL` (пробелы ставятся кнопкой TAB). И для того, чтобы выйти из конфигурационного фалйа и сохранить его, нужно нажать кнопку `ESC` и написать следующую команду `:wq!` (рис. 2).

<div align="center">
   <img src="https://github.com/user-attachments/assets/a037c29a-83c4-42f0-88af-62bbbb916a9b" alt="" width="500">
   <p>Рисуок 2 - Конфигурационный файл sudoers </p>
</div>

После всех этих манипуляций повторно прописываем команду `sudo yam istall wget` и для того, чтобы убедиться, что она скачена, прописываем команду `wget --version` (рис. 3).

<div align="center">
   <img src="https://github.com/user-attachments/assets/1d13b881-0e6c-4975-8af8-a9871c85c74b" alt="" width="500">
   <p>Рисунок 3 - wget</p>
</div>

## Задание 2 ##
Прописываем команду `sudo yam install curl`, дабы убедиться, что библиотека curl скачена на виртуальную машину (рис. 4).

<div align="center">
   <img src="https://github.com/user-attachments/assets/045fa605-3f01-44b9-9f08-26e8e95335bc" alt="" width="1000">
   <p>Рисунок 4 - curl</p>
</div>

Дальше по заданию прописываем команду `sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`. Данная команда устанавливает репозиторий docker по следующему пути: /etc/yum.repos.d/ в виртуальную машину (рис. 5).

<div align="center">
   <img src="https://github.com/user-attachments/assets/5ea3ce1b-2b08-4406-ae85-3ff54795f2cf" alt="" width="1000">
   <p>Рисунок 5 - Репозиторий docker</p>
</div>

Следующий шагом нужно будет установить сам docker командой `sudo yum install docker-ce docker-ce-cli containerd.io` (рис. 6).

<div align="center">
   <img src="https://github.com/user-attachments/assets/6612cbe1-3369-4a6b-8f0c-e331e1c305d1" alt="" width="1000">
   <p>Рисунок 6 - docker</p>
</div>

Следующая команда даёn разрешение на авто-запуск docker (рис. 7).
```bash
sudo systemctl enable docker --now
```

<div align="center">
   <img src="https://github.com/user-attachments/assets/dfaae9a9-3b28-49ad-839c-0b80bcaa99bc" alt="" width="1000">
   <p>Рисунок 7 - Авто-запуск docker</p>
</div>

## Задание 3 ##
Команда `COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)` получает последнюю версию Docker Compose, для этого использует API GitHub для получения информации о последнем релизе и вытаскивает номер версии из JSON ответа (рис. 8).

<div align="center">
   <img src="https://github.com/user-attachments/assets/df033843-1cd4-4f08-991a-33e5f0b1b8d6" alt="" width="1000">
   <p>Рисунок 8 - Команда для версии Docker Compose</p>
</div>

Команда `sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose` скачивает Docker Compose соответствующий системе, $(uname -s) - операционная система, $(uname -m) - архитектура процессора и сохраняет в /usr/bin/docker-compose (рис. 9).

<div align="center">
   <img src="https://github.com/user-attachments/assets/d9662de7-b656-40d7-bbaa-bb6c3980c41f" alt="" width="1000">
   <p>Рисунок 9 - Docker Compose</p>
</div>

`sudo chmod +x /usr/bin/docker-compose`

<div align="center">
   <img src="https://github.com/user-attachments/assets/847a641d-6d1d-43ae-8657-5deba3a92b9f" alt="" width="1000">
   <p>Рисунок 10 - Команда для версии Docker Compose</p>
</div>

`docker-compose --version`

<div align="center">
   <img src="https://github.com/user-attachments/assets/2422febb-bd3e-4581-ab55-254c0c4612c9" alt="" width="1000">
   <p>Рисунок 11 - Команда для версии Docker Compose</p>
</div>

Скачиваем git командой `sudo yum install git` (рис. 12).

<div align="center">
   <img src="https://github.com/user-attachments/assets/2c4e5670-ea50-4c5d-b777-38df02eb6e0d" alt="" width="1000">
   <p>Рисунок 12 - Команда для версии Docker Compose</p>
</div>

`git clone https://github.com/skl256/grafana_stack_for_docker.git`

<div align="center">
   <img src="https://github.com/user-attachments/assets/24a58d91-62c7-4851-8a04-f8d9a483d512" alt="" width="1000">
   <p>Рисунок 13 - Команда для версии Docker Compose</p>
</div>

`cd grafana_stack_for_docker`

<div align="center">
   <img src="https://github.com/user-attachments/assets/9e9d5805-b1a8-4c2d-88e5-4b0cb8d76673" alt="" width="1000">
   <p>Рисунок 14 - Команда для версии Docker Compose</p>
</div>

`sudo mkdir -p /mnt/common_volume/swarm/grafana/config`

<div align="center">
   <img src="https://github.com/user-attachments/assets/332b9115-9d8a-4841-a96a-b481c40183c2" alt="" width="1000">
   <p>Рисунок 15 - Команда для версии Docker Compose</p>
</div>

`sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}`

<div align="center">
   <img src="https://github.com/user-attachments/assets/bc11a335-6e76-43b6-954a-f21eb31ad178" alt="" width="1000">
   <p>Рисунок 16 - Команда для версии Docker Compose</p>
</div>

`sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}`

<div align="center">
   <img src="https://github.com/user-attachments/assets/b22ecb57-6d29-48eb-924d-fb5be8bf3d4f" alt="" width="1000">
   <p>Рисунок 17 - Команда для версии Docker Compose</p>
</div>

`touch /mnt/common_volume/grafana/grafana-config/grafana.ini`

<div align="center">
   <img src="https://github.com/user-attachments/assets/36eb8da9-e657-46f9-8c47-daad881b9dbe" alt="" width="1000">
   <p>Рисунок 18 - Команда для версии Docker Compose</p>
</div>

`cp config/* /mnt/common_volume/swarm/grafana/config/`

<div align="center">
   <img src="https://github.com/user-attachments/assets/3f366f71-13de-4622-bb9d-c5f476692988" alt="" width="1000">
   <p>Рисунок 19 - Команда для версии Docker Compose</p>
</div>

`mv grafana.yaml docker-compose.yaml`

<div align="center">
   <img src="https://github.com/user-attachments/assets/36802099-d178-4d9e-a694-ac65bf31e113" alt="" width="1000">
   <p>Рисунок 20 - Команда для версии Docker Compose</p>
</div>

`sudo docker compose up -d`

<div align="center">
   <img src="" alt="" width="1000">
   <p>Рисунок 21 - Команда для версии Docker Compose</p>
</div>
