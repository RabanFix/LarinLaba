# DavidovLaba
## Задание 1 ##
Была прописана команда `sudo yam istall wget`, после чего была получена ошибка `is not a sudoers life`.
Для начала заходим под супер пользователя командой `su`.
Данная ошибка решается путём команды `sudo vi /etc/sudoers`, которая открывает конфигурационный файл, и была добавлена следующая строчка "Larin ALL=(ALL) ALL"
![image](https://github.com/user-attachments/assets/a037c29a-83c4-42f0-88af-62bbbb916a9b)

