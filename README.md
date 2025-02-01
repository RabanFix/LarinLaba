# Laba
## Задание 1 ##
Была прописана команда `sudo yam istall wget`, после чего была получена ошибка `is not a sudoers life`(рис. 1).


Для этого, сначала заходим под супер пользователя командой `su` (рис. 2).

<div align="center">
   <img src="https://github.com/user-attachments/assets/c363c8b5-4aee-4d9b-a664-0fcc9f36602e" alt="" width="500">
   <p>Рисунок 1 - Супер пользователь</p>
</div>

Данная ошибка решается путём команды `sudo vi /etc/sudoers`, которая открывает конфигурационный файл, и была добавлена следующая строчка `Larin  ALL=(ALL)  ALL` (пробелы ставятся кнопкой TAB). И для того, чтобы выйти из конфигурационного фалйа и сохранить его, нужно нажать кнопку `ESC` и написать следующую команду `:wq!` (рис. 3).

<div align="center">
   <img src="https://github.com/user-attachments/assets/a037c29a-83c4-42f0-88af-62bbbb916a9b" alt="" width="500">
   <p>Рисуок 3 - Конфигурационный файл sudoers </p>
</div>

После всех этих манипуляций, повторно прописываем команду `sudo yam istall wget`, и для того, чтобы убедиться, что она скачена прописываем команду `wget --version` (рис. 4).

<div align="center">
   <img src="https://github.com/user-attachments/assets/1d13b881-0e6c-4975-8af8-a9871c85c74b" alt="" width="500">
   <p>Рисунок 4 - wget</p>
</div>
