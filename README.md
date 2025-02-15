# Laba
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
`COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)`


`sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose`


`sudo chmod +x /usr/bin/docker-compose`


`docker-compose --version`


`git clone https://github.com/skl256/grafana_stack_for_docker.git`


`cd grafana_stack_for_docker`


`sudo mkdir -p /mnt/common_volume/swarm/grafana/config`


`sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}`


`touch /mnt/common_volume/grafana/grafana-config/grafana.ini`


`cp config/* /mnt/common_volume/swarm/grafana/config/`


`mv grafana.yaml docker-compose.yaml`


`sudo docker compose up -d`
