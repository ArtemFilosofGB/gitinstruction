![GitLogo](/images/git-logo.png)
# Инструкция по работе с Git

Git - это распределенная система контроля версий, которая широко используется для управления и отслеживания изменений в исходном коде проектов. Вот некоторые консольные команды Git, которые помогут вам в работе с репозиторием.

*Простыми словами: Git - это твой помощник в работе с проектами. Он поможет тебе не потерять ничего на каждой стадии работы. И абсолютно незаменим для коммандных проектов.*

## Установка и настройка Git
1. Скачайте Git с официального сайта и установите его на свою систему.
2. Проверьте, установлен ли Git, выполнив команду:
   ```
   git --version
   ```
3. Настройте свое имя пользователя и адрес электронной почты для использования в Git.:
   ```
   git config --global user.name "Ваше имя"
   git config --global user.email "ваша-почта@exampleNO LINKS"
   ```
*После установки необходимо «представиться» системе контроля версий. Это нужно сделать всего один раз, и git запомнит вас. Для этого нужно ввести в терминале 2 команды*
## Основные команды Git
### Создание репозитория
Репозиторий Git или репозиторий — это папка, в которую Git отслеживает изменения. На компьютере может быть любое количество репозиториев, каждое из которых хранится в собственной папке. Каждый репозиторий Git в системе является независимым, поэтому изменения, сохраненные в одном репозитории Git, не влияют на содержимое другого.

Репозиторий Git содержит каждую версию каждого файла, сохраненного в репозитории.
1. Создайте новый локальный репозиторий с помощью команды:
   ```
   git init
   ```
2. Добавьте файлы в репозиторий:
   ```
   git add <файлы>
   ```
3. Зафиксируйте изменения в репозитории:
   ```
   git commit -m "Ваше сообщение о коммите"
   ```

### Отслеживание изменений
1. Отобразить статус репозитория:
   ```
   git status
   ```
2.  Показать историю всех сохраниний commit. В случае когда список всех изменений не помещается в окно терминала, требуется пролистать список до конца (Нажимая клавишу пробел). Выход из меню - "q" (от слова quit)
    ```
    git log  //выводит историю изменений

    git log --graph //выводит историю изменений в виде дерева

    git log --all --graph //выводит дерево со всеми ветвями
    ```
    ## Ещё несколько полезных вариантов git log

    ```
            git log --all --oneline \\граф в одну линнию
            
            git restore <имя файла> - откатить изменения в файле если были внесены изменения
            
            git log --all --oneline —graph \\представление из любой ветки (shift+6 ENG)
            
            git log —p —all все изменения
            
            git checkout branch^ \\предпоследний комит ветки
    ```
    
     <details><summary>Подробнее о git log</summary>

      Команда `git log` используется для просмотра истории коммитов в репозитории Git. Она позволяет просмотреть список коммитов в обратном хронологическом порядке, а также получить информацию о каждом коммите, такую как автор, дата и время создания, и сообщение коммита.

      Вот подробная инструкция по использованию команды `git log`:

      1. Откройте командную строку или терминал и перейдите в директорию вашего репозитория Git.

      2. Введите следующую команду:

         ```
         git log
         ```

         Это покажет вам полный список коммитов в репозитории, начиная с самого последнего.

         Пример вывода:

         ```
         commit 3e4a1c63e295cf4f0c7c62f0b5c5ac4973f9d9a3
         Author: John Doe <johndoe@exampleNO LINKS>
         Date:   Tue Feb 16 15:30:00 2021 +0300

            Added new feature

         commit c8c9f9b81d927b6a2e83a237b13d18a279bdff54
         Author: Jane Smith <janesmith@exampleNO LINKS>
         Date:   Mon Feb 15 10:45:00 2021 +0300

            Fixed bug in login page
         ```

         Каждый коммит представлен информацией, которая включает в себя хеш коммита, автора, дату и время создания коммита, а также сообщение коммита.

      3. Дополнительные опции команды `git log`:

         - `--oneline`: выводит каждый коммит в одной строке, содержащей только хеш коммита и сообщение коммита. Это удобно для просмотра большого количества коммитов на экране.
         - `--author`: фильтрует коммиты по имени автора. Например, `git log --author="John Doe"` отобразит только коммиты, сделанные автором "John Doe".
         - `--since` и `--until`: фильтруют коммиты по диапазону дат. Например, `git log --since="2021-02-15"` отобразит только коммиты, сделанные после указанной даты.
         - `--grep`: фильтрует коммиты по тексту в сообщении коммита. Например, `git log --grep="bug"` отобразит только коммиты, содержащие слово "bug" в сообщении.

         Примеры использования дополнительных опций:

         ```
         git log --oneline
         git log --author="John Doe"
         git log --since="2021-02-15" --until="2021-02-20"
         git log --grep="bug"
         ```

         Вы можете комбинировать эти опции, чтобы получить более точный и нужный вам результат.

      Это подробное руководство поможет вам использовать команду `git log` для просмотра истории коммитов в вашем репозитории Git.

      </details>
4. Показать различия между рабочей директорией и индексом:
   ```
   git diff ключ
   ```
5. Показать различия между индексом и последним коммитом:
   ```
   git diff --staged
   ```
6. Проверить состояние по сохранённому статусу (commit). Атрибуты - первые 4 цифры ключа commit, например ключ c362f8316d79c7e18833cb479ae777ffd2e7ec80, достаточно ввести: c362.
    ```
    git checkout ключ
    ```
7. Возвращает в ветку мастер
    ```
    git checkout master
    ```
   
### Работа с ветками
1. Создание новой ветки:
   ```
   git branch <имя_ветки>
   ```
2. Переключение на другую ветку:
   ```
   git checkout <имя_ветки>
   ```
3. Создание новой ветки и переключение на нее:
   ```
   git checkout -b <имя_ветки>
   ```
4. Удаление ветки:
   ```
   git branch -d <имя_ветки>
   ```
5. Слияние веток:
   ```
   git merge <имя_ветки>
   ```

      Вот подробная инструкция по использованию команды `git merge` с примерами:

   1. Сперва, убедитесь, что вы находитесь в нужной ветке, в которую вы хотите влить изменения. Вы можете проверить текущую ветку с помощью команды `git branch`.

   2. Затем, используйте команду `git merge` для слияния другой ветки в текущую ветку. Синтаксис команды `git merge` выглядит следующим образом:
      ```
      git merge <имя_ветки>
      ```

   3. Если конфликты слияния возникнут, Git попытается автоматически их разрешить. Однако, иногда требуется вмешательство пользователя для разрешения конфликтов. Вы можете использовать команду `git status`, чтобы увидеть, какие файлы вызывают конфликты. 

![Пример конфликта слияния](./images/conflict.JPG)

      Для разрешения конфликта слияния вручную требуется переместиться на предложенный фрагмент текста и выбрать одно из действий:  
      * Accept Curent changes - Принять версию из текущей ветви
      * Accept Incomming changes - Принять версию из входящей ветви
      * Accept Both changes - Оставить оба варианта 
      * Compare changes - Слиять изменения

   4. Когда все конфликты разрешены, добавьте изменения в индекс с помощью команды `git add`.

   5. Затем, сделайте коммит слияния, используя команду `git commit`. Git автоматически создаст сообщение коммита с информацией о слиянии.

   6. Ваше слияние завершено! Вы можете опубликовать изменения на удаленный сервер с помощью команды `git push`, если это необходимо.

      Теперь рассмотрим несколько примеров:

      Пример 1: Слияние ветки feature в текущую ветку
      ```
      $ git checkout main
      $ git merge feature
      ```

      Пример 2: Разрешение конфликтов перед слиянием
      ```
      $ git checkout main
      $ git merge feature
      $ git status (показывает файлы с конфликтами)
      $ vim file.txt (редактируете, разрешая конфликты)
      $ git add file.txt
      $ git status (проверяете, что все конфликты разрешены)
      $ git commit
      ```

      Пример 3: Слияние с удаленной веткой
      ```
      $ git fetch origin (получаете последние изменения с удаленного сервера)
      $ git merge origin/feature (сливаете удаленную ветку feature в текущую ветку)
      ```

   *Это основы использования команды `git merge`. Надеюсь, эта инструкция будет полезной!*

### Отправка изменений в удаленный репозиторий
1. Отправка изменений на сервер:
   ```
   git push <название_удаленного_репо> <имя_ветки>
   ```

### Отслеживание изменений
1. Отобразить статус репозитория:
   ```
   git status
   ```
2. Показать различия между рабочей директорией и индексом:
   ```
   git diff
   ```
3. Показать различия между индексом и последним коммитом:
   ```
   git diff --staged
   ```
## Пример команд для удалённой синхронизации с GitHub
      
      git init
      git add README.md
      git commit -m "first commit"
      git branch -M main
      git remote add origin https://github.com/ArtemFilosofGB/gitinstruction.git
      git push -u origin main

## Практика работы с удалённым репозиторием

- Комбинация команд «fork + git clone» используется для создания копии репозитория из исходного репозитория в вашу собственную учетную запись GitHub, а «fork + git pull» используется для обновления локальной копии клонированного репозитория. из вашей учетной записи GitHub.
- Вот некоторые ключевые различия между этими двумя комбинациями:
1. Форк + клон git:
    - Форкирование репозитория создает отдельную копию исходного репозитория в вашей учетной записи GitHub.
    - Затем клон Git используется для создания локальной копии репозитория из вашей учетной записи GitHub на ваш локальный компьютер.
    — Эта комбинация обычно используется, когда вы хотите внести свой вклад в проект, внеся изменения в свою собственную копию репозитория.
2. Форк + git pull:
    - Форкирование репозитория по-прежнему создает отдельную копию исходного репозитория в вашей учетной записи GitHub.
    — Однако вместо клонирования репозитория на локальный компьютер вы используете git pull для обновления существующей локальной копии репозитория, которая ранее была клонирована из вашей учетной записи GitHub.
    — Эта комбинация обычно используется, когда вы уже клонировали репозиторий и хотите получить последние изменения из исходного репозитория.
    
    Таким образом, «fork + git clone» используется для создания локальной копии репозитория из вашей собственной учетной записи GitHub, а «fork + git pull» используется для обновления существующей локальной копии репозитория, которая ранее была клонирована из вашей собственной. Аккаунт на GitHub.

# Обработка ошибок 
## git push -->  ![rejected]
   ```
P:\IT\Знакомство с языком программирования С#\Sem1\Task06>git push
To https://github.com/ArtemFilosofGB/sem1.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/ArtemFilosofGB/sem1.git'
   ```

### Исправление оибки _rejected_
Ошибка из-за того, что на сервере есть изменения, которых у Вас нет в локальном хранилище.
   ```
Нужно сделать git pull перед git push.
   ```

 Это лишь некоторые из доступных команд Git. Вы можете ознакомиться с полным списком команд и дополнительной документацией в официальной документации [Git](https://docs.github.com/ru/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

 Или записаться на обучение в [GeekBrains](https://gb.ru/).

Автор инструкции: afilosof1@gmail.com

При поддержке: Влеленский цифровой ум №4 

<image src="https://api.wakool.id/images/thumb200/20200716030745git_1623730694.png" alt="Logo по ссылке">
