# Лабораторная работа
## Задание 1

```bash
sudo yum install wget
```

Что делает эта команда:
- `sudo` : Выполняет команду с правами суперпользователя (root). Это необходимо для установки программного обеспечения, так как изменения в системе требуют повышенных привилегий.
- `yum` : Это пакетный менеджер, используемый в дистрибутивах Linux на базе Red Hat. Он управляет установкой, обновлением и удалением программ.
- `install` : Подкоманда yum, которая устанавливает указанный пакет.
- `wget` : Это программа для загрузки файлов с интернета. Она поддерживает протоколы HTTP, HTTPS и FTP, а также может скачивать файлы по ссылкам рекурсивно.

После чего была получена ошибка `is not in the sudoers file`. Эта ошибка означает, что текущий пользователь не имеет прав на выполнение команд с использованием sudo.

Чтобы исправить эту ошибку используем следующие команды:
```bash
su
```

- Команда `su` используется в Linux и других Unix-подобных операционных системах для смены текущего пользователя. Она позволяет временно получить права другого пользователя, включая привилегии суперпользователя (root) (рис. 1).

<div align="center">
   <img src="https://github.com/user-attachments/assets/c363c8b5-4aee-4d9b-a664-0fcc9f36602e" alt="" width="500">
   <p>Рисунок1 - Супер пользователь</p>
</div>

После же прописываем команду: 
```bash
sudo vi /etc/sudoers
```

Что делает команда пошагово:
- `sudo` : Выполняет команду с правами суперпользователя.
- `vi` : Это текстовый редактор, который используется для изменения содержимого файла.
- `/etc/sudoers` : Это конфигурационный файл, который определяет правила для использования команды sudo. Файл содержит список пользователей и групп, которым разрешено выполнять определённые действия от имени root, а также ограничения на эти действия. То есть, была добавлена следующая строчка `Larin  ALL=(ALL)  ALL`. И для того, чтобы выйти из конфигурационного фалйа и сохранить его, нужно нажать сочетание `Shift + ;` и написать следующую команду `wq!` (рис. 2).

<div align="center">
   <img src="https://github.com/user-attachments/assets/a037c29a-83c4-42f0-88af-62bbbb916a9b" alt="" width="500">
   <p>Рисуок 2 - Конфигурационный файл sudoers </p>
</div>

После всех этих манипуляций повторно прописываем повторно команду: 
```bash
sudo yum install wget
```

И для того, чтобы убедиться, что она скачена, прописываем команду (рис. 3)
```bash
wget --version
```

<div align="center">
   <img src="https://github.com/user-attachments/assets/1d13b881-0e6c-4975-8af8-a9871c85c74b" alt="" width="500">
   <p>Рисунок 3 - wget</p>
</div>

---
## Задание 2

```bash
sudo yum install curl
```

Разберем команду по частям:
- `sudo` : Выполняет команду с правами суперпользователя (root).
- `yum` : Это пакетный менеджер, который автоматически обрабатывает установку, удаление и обновление программного обеспечения.
- `install` : Подкоманда yum, которая указывает на установку указанного пакета.
- `curl` : Это программа командной строки для передачи данных через различные протоколы (например, HTTP, HTTPS, FTP). Она часто используется для выполнения HTTP-запросов, загрузки файлов или тестирования API. (рис. 4).

<div align="center">
   <img src="https://github.com/user-attachments/assets/045fa605-3f01-44b9-9f08-26e8e95335bc" alt="" width="1000">
   <p>Рисунок 4 - curl</p>
</div>


```bash
sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo
```

- `-P /etc/yum.repos.d/` : Флаг -P указывает директорию, куда будет сохранен скачанный файл. В данном случае файл будет сохранен в /etc/yum.repos.d/, где хранятся конфигурационные файлы репозиториев для yum.
- `https://download.docker.com/linux/centos/docker-ce.repo` : Это URL-адрес файла репозитория Docker для CentOS. Файл docker-ce.repo содержит информацию о репозитории Docker, включая расположение пакетов и их версии.(рис. 5).

<div align="center">
   <img src="https://github.com/user-attachments/assets/5ea3ce1b-2b08-4406-ae85-3ff54795f2cf" alt="" width="1000">
   <p>Рисунок 5 - Репозиторий docker</p>
</div>

```bash
sudo yum install docker-ce docker-ce-cli containerd.io
```

- `docker-ce` : Это основной пакет Docker Community Edition (CE), который содержит саму программу Docker. Он позволяет создавать, запускать и управлять контейнерами.
- `docker-ce-cli` : Этот пакет содержит командную строку Docker (docker), которая используется для взаимодействия с Docker-демоном. Он отделяет интерфейс командной строки от основного пакета для большей гибкости.
- `containerd.io` : Это низкоуровневая система управления контейнерами, используемая Docker для запуска и управления контейнерами. Она обеспечивает базовую функциональность для работы с контейнерами. (рис. 6).

<div align="center">
   <img src="https://github.com/user-attachments/assets/6612cbe1-3369-4a6b-8f0c-e331e1c305d1" alt="" width="1000">
   <p>Рисунок 6 - docker</p>
</div>

```bash
sudo systemctl enable docker --now
```

- Команда даёт на авто-запуск докера (рис. 7).

<div align="center">
   <img src="https://github.com/user-attachments/assets/dfaae9a9-3b28-49ad-839c-0b80bcaa99bc" alt="" width="1000">
   <p>Рисунок 7 - Авто-запуск docker</p>
</div>

---
## Задание 3

```bash
COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)
```
- `COMVER=$( ... )` : Это команда для присвоения значения переменной COMVER. Результат выполнения команды внутри $() будет сохранён в переменную COMVER
- `curl -s https://api.github.com/repos/docker/compose/releases/latest` :
   - `curl` : Утилита для выполнения HTTP-запросов.
   - `-s` : Флаг, который подавляет вывод прогресса и предупреждений (silent mode).
   - `https://api.github.com/repos/docker/compose/releases/latest` : URL API GitHub, который возвращает информацию о последнем релизе проекта Docker Compose. Ответ представляет собой JSON-объект с информацией о версии, дате выпуска, ссылках на скачивание и т.д. (рис. 8).

<div align="center">
   <img src="https://github.com/user-attachments/assets/df033843-1cd4-4f08-991a-33e5f0b1b8d6" alt="" width="1000">
   <p>Рисунок 8 - Команда для версии Docker Compose</p>
</div>

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
```

- `curl -L` :
   - `curl` : Утилита для выполнения HTTP-запросов.
   - `-L` : Флаг, который указывает curl следовать перенаправлениям (редиректам). Это важно, потому что GitHub может перенаправить запрос на фактическое местоположение файла.
- `"https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)"` : Это URL для скачивания Docker Compose.
- `-o /usr/bin/docker-compose` :
   - `-o` : Указывает, куда сохранить скачанный файл.
   - `/usr/bin/docker-compose` : Путь, куда будет сохранён исполняемый файл Docker Compose. Каталог `/usr/bin/` является стандартным местом для глобальных исполняемых файлов.

Разбираем URL:

- `https://github.com/docker/compose/releases/download/` : Базовый URL для загрузки релизов Docker Compose с GitHub.
- `$COMVER` : Переменная, содержащая версию Docker Compose. Например, если $COMVER=v2.17.2, то URL будет содержать /v2.17.2/.
- `docker-compose-$(uname -s)-$(uname -m)` :
   - `$(uname -s)` : Возвращает название операционной системы (например, Linux).
   - `$(uname -m)` : Возвращает архитектуру процессора (например, x86_64 или arm64).(рис. 9).

<div align="center">
   <img src="https://github.com/user-attachments/assets/d9662de7-b656-40d7-bbaa-bb6c3980c41f" alt="" width="1000">
   <p>Рисунок 9 - Docker Compose</p>
</div>

```bash
sudo chmod +x /usr/bin/docker-compose
```

- `chmod` : Это команда для изменения прав доступа к файлам и директориям. Права доступа определяют, кто может читать, записывать или выполнять файл.
- `+x` : Флаг `+x` добавляет право на выполнение (execute) для всех пользователей (владельца, группы и других). После применения этого флага файл становится исполняемым, то есть его можно запускать как программу или скрипт.
- `/usr/bin/docker-compose` : Это путь к файлу `docker-compose` , который был ранее загружен (например, с помощью команды curl) и сохранён в системную директорию /usr/bin/. Каталог `/usr/bin/` является стандартным местом для хранения глобальных исполняемых файлов в Linux (рис. 10).

<div align="center">
   <img src="https://github.com/user-attachments/assets/847a641d-6d1d-43ae-8657-5deba3a92b9f" alt="" width="1000">
   <p>Рисунок 10 - Команда для версии Docker Compose</p>
</div>

```bash
docker-compose --version
```

- `docker-compose` : Это основная команда для управления контейнерами с помощью Docker Compose. Docker Compose позволяет определять и запускать многоступенчатые приложения Docker с несколькими контейнерами через файл конфигурации (обычно docker-compose.yml).
- `--version` : Подкоманда, которая запрашивает информацию о версии Docker Compose. Выводит номер версии, чтобы пользователь мог убедиться, что установлена нужная версия (рис. 11).

<div align="center">
   <img src="https://github.com/user-attachments/assets/2422febb-bd3e-4581-ab55-254c0c4612c9" alt="" width="1000">
   <p>Рисунок 11 - Команда для версии Docker Compose</p>
</div>

```bash
sudo yum install git
```

 - Данная команда устанавливает пакет git (рис. 12).

<div align="center">
   <img src="https://github.com/user-attachments/assets/2c4e5670-ea50-4c5d-b777-38df02eb6e0d" alt="" width="1000">
   <p>Рисунок 12 - Команда для версии Docker Compose</p>
</div>

```bash
git clone https://github.com/skl256/grafana_stack_for_docker.git
```

- `git clone` : Подкоманда Git, которая создает локальную копию удаленного репозитория. После выполнения этой команды Git скачивает весь проект, включая его историю коммитов, ветки и теги.
- `https://github.com/skl256/grafana_stack_for_docker.git` : URL-адрес удаленного репозитория на GitHub. Этот адрес указывает на репозиторий под названием grafana_stack_for_docker (рис. 13).

<div align="center">
   <img src="https://github.com/user-attachments/assets/24a58d91-62c7-4851-8a04-f8d9a483d512" alt="" width="1000">
   <p>Рисунок 13 - Команда для версии Docker Compose</p>
</div>

```bash
cd grafana_stack_for_docker
```

- Данная команда переводит нас на директорию `grafana_stack_for_docker` (рис. 14).

<div align="center">
   <img src="https://github.com/user-attachments/assets/9e9d5805-b1a8-4c2d-88e5-4b0cb8d76673" alt="" width="1000">
   <p>Рисунок 14 - Команда для версии Docker Compose</p>
</div>

```bash
sudo mkdir -p /mnt/common_volume/swarm/grafana/config
```

- `mkdir` : Это команда для создания новых директорий (папок) в Linux.
- `-p` : Флаг -p (от "parents") означает, что команда создаст не только указанную директорию, но и все необходимые родительские директории, если они ещё не существуют. Например, если путь `/mnt/common_volume/swarm/grafana/` не существует, команда автоматически создаст его целиком.
- `/mnt/common_volume/swarm/grafana/config` : Полный путь к новой директории, которую нужно создать (рис. 15).

<div align="center">
   <img src="https://github.com/user-attachments/assets/332b9115-9d8a-4841-a96a-b481c40183c2" alt="" width="1000">
   <p>Рисунок 15 - Команда для версии Docker Compose</p>
</div>

```bash
sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}
```

- `/mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}` : Это использование brace expansion — механизма оболочки bash для генерации списка значений из фигурных скобок. `{grafana-config,grafana-data,prometheus-data}` раскрывается в три отдельные строки: grafana-config, grafana-data и prometheus-data.

Зачем это нужно?
Эта команда часто используется при настройке среды для работы с Docker, Grafana и Prometheus. Вот примеры использования каждой из создаваемых директорий:
- `grafana-config` : Используется для хранения конфигурационных файлов Grafana, например, grafana.ini или файлов дашбордов.
- `grafana-data` :Используется для хранения данных Grafana, таких как база данных SQLite (по умолчанию) и сохранённые дашборды.
- `prometheus-data` : Используется для хранения данных Prometheus, таких как временные ряды метрик (рис. 16).

<div align="center">
   <img src="https://github.com/user-attachments/assets/bc11a335-6e76-43b6-954a-f21eb31ad178" alt="" width="1000">
   <p>Рисунок 16 - Команда для версии Docker Compose</p>
</div>

```bash
sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}
```

- `chown` : Это команда для изменения владельца и/или группы файла или директории.
- `-R` : Флаг `-R` (от "recursive") означает, что изменения будут применены рекурсивно ко всем файлам и поддиректориям внутри указанной директории.
- `$(id -u):$(id -g)` : Это выражение определяет нового владельца и группу для файлов.
- `{/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}` : Это использование brace expansion (расширения фигурных скобок) для одновременного указания нескольких путей. `{path1,path2}` раскрывается в два отдельных пути: `/mnt/common_volume/swarm/grafana/config` и `/mnt/common_volume/grafana` (рис. 17).


<div align="center">
   <img src="https://github.com/user-attachments/assets/b22ecb57-6d29-48eb-924d-fb5be8bf3d4f" alt="" width="1000">
   <p>Рисунок 17 - Команда для версии Docker Compose</p>
</div>

```bash
touch /mnt/common_volume/grafana/grafana-config/grafana.ini
```

- `touch` : Это команда для создания новых файлов или обновления метки времени существующих файлов.
   - Если файл не существует, touch создаст его пустым.
   - Если файл уже существует, touch просто обновит дату последнего доступа и изменения (timestamp).
- `/mnt/common_volume/grafana/grafana-config/grafana.ini` : Полный путь к файлу, который нужно создать или обновить. В данном случае это файл конфигурации Grafana `(grafana.ini)`, расположенный в директории `/mnt/common_volume/grafana/grafana-config/` (рис. 18).

<div align="center">
   <img src="https://github.com/user-attachments/assets/36eb8da9-e657-46f9-8c47-daad881b9dbe" alt="" width="1000">
   <p>Рисунок 18 - Команда для версии Docker Compose</p>
</div>

```bash
cp config/* /mnt/common_volume/swarm/grafana/config/
```

- `cp` : Это команда для копирования файлов и директорий в Linux.
- `config/*` : Указывает на все файлы (но не поддиректории) внутри директории config. Звёздочка (*) — это шаблон, который означает "все файлы" в указанной директории. Если директория config содержит файлы `file1.txt`, `file2.conf` и `file3.log` и т.п., то этот шаблон будет соответствовать всем этим файлам.
- `/mnt/common_volume/swarm/grafana/config/` : Это целевая директория, куда будут скопированы файлы из `config` (рис. 19).

<div align="center">
   <img src="https://github.com/user-attachments/assets/3f366f71-13de-4622-bb9d-c5f476692988" alt="" width="1000">
   <p>Рисунок 19 - Команда для версии Docker Compose</p>
</div>

```bash
mv grafana.yaml docker-compose.yaml
```

- `mv` : Это стандартная Unix-команда для перемещения или переименования файлов и директорий.
  - Если указать один путь (например, mv file.txt newfile.txt), она переименует файл.
  - Если указать два разных пути (например, mv file.txt /another/directory/), она переместит файл.
- `grafana.yaml` : Это исходный файл, который вы хотите переименовать. В данном случае это файл конфигурации Grafana, написанный в формате YAML.
- `docker-compose.yaml` : Это новое имя файла, которое будет использоваться вместо старого. В данном случае это стандартное имя для файла конфигурации Docker Compose.

<div align="center">
   <img src="https://github.com/user-attachments/assets/36802099-d178-4d9e-a694-ac65bf31e113" alt="" width="1000">
   <p>Рисунок 20 - Команда для версии Docker Compose</p>
</div>

```bash
sudo docker compose up -d
```
- `sudo` : Это команда для выполнения операции с правами суперпользователя (root), если текущий пользователь не добавлен в группу docker.
- `docker compose` : Это подкоманда Docker Compose, которая используется для управления мультиконтейнерными приложениями через файл docker-compose.yml.
- `up` : Эта команда создает и запускает контейнеры, описанные в файле docker-compose.yml. Если контейнеры уже существуют, они просто запускаются.
- `-d` (detached mode): Этот флаг указывает Docker Compose запускать контейнеры в фоновом режиме, без вывода логов в терминал. Это удобно для длительных задач или продакшн-сценариев.

<div align="center">
   <img src="https://github.com/user-attachments/assets/a6d9dd9c-eab3-4032-9fc9-c5af6e52dffc" alt="" width="1000">
   <p>Рисунок 21 - Команда для поднятия Docker Compose</p>
</div>

---
## Задание 4

```bash
sudo docker compose up -d
```

- Данная команда с ключом `-d` переводит автоматически docker compose в фоновый режим (рис. 22).

<div align="center">
   <img src="https://github.com/user-attachments/assets/6d3f8cc2-db0c-4ea0-9ee1-4219b737f76a" alt="" width="1000">
   <p>Рисунок 22 - Docker Compose</p>
</div>

```bash
sudo docker compose stop
```

- Эта команда останавливает все активные контейнеры, связанные с проектом, который описан в файле `docker-compose.yml` (рис. 23).

<div align="center">
   <img src="https://github.com/user-attachments/assets/44c86d1b-56af-4e80-99b4-d20b93babf74" alt="" width="1000">
   <p>Рисунок 23 - Остановка Docker Compose через stop</p>
</div>

```bash
sudo docker compose down
```

Эта команда выполняет следующие действия:
- Останавливает все активные контейнеры, связанные с проектом.
- Удаляет контейнеры.
- Удаляет сети, созданные автоматически для этого проекта.
- По умолчанию не удаляет объёмы (volumes) и образы (images), если они явно не указаны в параметрах (рис. 24).

<div align="center">
   <img src="https://github.com/user-attachments/assets/6596b41c-60da-490f-adfb-e1d88ea8d465" alt="" width="1000">
   <p>Рисунок 24 - Остановка Docker Compose через down</p>
</div>

```bash
sudo docker compose ps
```

- Эта команда выводит список контейнеров, которые относятся к текущему проекту, вместе с их состоянием и дополнительной информацией (рис. 25).

<div align="center">
   <img src="https://github.com/user-attachments/assets/b8f60e84-2490-4988-8cd2-88079964742b" alt="" width="1000">
   <p>Рисунок 25 - Список контейнеров</p>
</div>

```bash
git clone https://github.com/RabanFix/LarinLaba.git
```

- Благодаря этой команде успашно создана папка с наименованием "LarinLaba" (рис. 26).

<div align="center">
   <img src="https://github.com/user-attachments/assets/c9ddca58-88aa-4fda-99a5-8eebe392b638" alt="" width="1000">
   <p>Рисунок 26 - Папка LarinLaba </p>
</div>

```bash
pwd
```

- Команда `pwd` (от p rint w orking d irectory) используется для вывода текущей рабочей директории (путь к той папке, в которой вы находитесь в данный момент в терминале) (рис. 27).

<div align="center">
   <img src="https://github.com/user-attachments/assets/36fd569f-2650-4f07-bf8a-f0512c57f00a" alt="" width="1000">
   <p>Рисунок 27 - Полный путь </p>
</div>

---
## Задание 5

```bash
sudo mv prometeus.yaml /mnt/common_volume/swarm/grafana/config/
```

- Команда переносит файл `prometeus.yaml` в папку по пути `/mnt/common_volume/swarm/grafana/config/`. 

<div align="center">
   <img src="https://github.com/user-attachments/assets/b326d956-5c3b-4809-b8cb-cb4c07b5f42d" alt="" width="1000">
   <p>Рисунок 28 - Перенос файла прометеуса </p>
</div>
