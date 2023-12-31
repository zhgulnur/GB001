# Инструкции по работе с Git

## Знакомство

При открытии Visual Studio Code, на главной странице, нужно открыть папку, где вы будете работать. 
P.S. Лучше чтобы это была новая папка для каждой задачи.

После открытия создаем файл markdowm (.md) и работаем через терминал.

Для инициализации Git набираем: _**git init**_

Также нам нужно представиться с помощью команды _**git config --global user.name "ваше_имя"**_

И еще нужно установить email: _**git config --global user.email "адрес_почты@email.com"**_

## Первые команды

Для того, чтобы узнать версию git, который установлен у вас: _**git --version**_

Для того, чтобы узнать, что Git думает о нашей папке и её содержимом, а также статус происходящего: _**git status**_

Чтобы добавить файл (любой в этой папке) для дальнейшего отслеживания: _**git add НазваниеФайла**_ (можно начать писать название файла и нажать Tab, оно автоматически допишется).

Также лучше выбрать опцию "Автосохранение" во вкладке Файл, чтобы не мучаться с сохранением каждый раз, когда вносятся изменения.

Можно не писать каждый раз команды целиком, если вы ранее писали их. Можно нажать кнопку "вверх", там есть "история команд".

Когда файл меняется, нужно обязательно закомиттить изменения, которые произошли. Для этого пишем _**git commit -am "Ваше сообщение на русском или английском"**_

## Работа с разными версиями

Для просмотра журнала изменений: _**git log**_

Для перехода в другую версию файла: _**git checkout**_ названиеФайла (можно узнать в журнале)

Для возвращения в текущую версию: _**git checkout master**_ (если вы работали в ветке master)

Для просмотра разницы текущего файла с сохраненным: _**git diff**_

_**clear**_ - чистит терминал VSCode

## Работа с ветками

_**git branch названиеВетки**_  - для создания новой ветки

_**git branch**_  - для того, чтобы посмотреть какие ветки есть. Зеленый, который подмечен звездочкий - тот, где вы находитесь на данный момент.

_**git checkout названиеВетки**_  - для перехода на другую ветку

_**git branch -d названиеВтки**_  - для удаления ветки

_**git branch -D названиеВетки**_  - для удаления ветки, даже если она не полностью слилась. Лучше удалять через маленькую, чтобы не удалить случайно что-нибудь

_**git merge названиеВетки**_  - для слияния ветки с той, в которой вы находитесь. То есть, нужно вернуться в master (ведь основная работа проводится там, по логике)

_**git config branch.autosetuprebase always # Force all new branches to automatically use rebase**_  - для того, чтобы ветки автоматически сливались без выхода сообщения вроде _"Please enter a commit message to explain why this merge is necessary, # especially if it merges an updated upstream into a topic branch."_

Если такое сообщение все же вышло:

1. press i (i for insert)
2. write your merge message
3. press esc (escape)
4. write :wq (write & quit)
5. then press enter

Например: i Merged lists with the master branch **(esc_)** :wq **(enter)**

## Выделение текста

Чтобы выделить текст курсивом, необходимо обрамить его звездочками (*). Например, *вот так*.

Чтобы выделить текст полужирным, необходимо обрамить его двойными звездочками (**). Например, **вот так**.

Альтернативно можно выделить курсивом текст с нижним пробелом с двух сторон. Например, _вот так_.

Также альтернативно можно выделить текст полужирным с помощься двух нижних пробелов с двух сторон. Например, __вот так__.

Это нужно для того, чтобы можно было выделить текст и курсивом, и жирным. Например, _**вот так**_.


## Списки

Чтобы добавить ненумерованные списки, необходимо пункты выделить звездочкой (*) или знаком +. Например, вот так:
* Элемент 1
* Элемент 2
* Элемент 3
+ Элемент 4
+ Элемент 5


Чтобы добавить нумерованные списки, необходимо пункты пронумеровать. Например, вот так:
1. Первый пункт
2. Второй пункт

## Работа с изображениями

Изображение можно вставить так:
![Switzerland.jpeg](Switzerland.jpeg)

В [] этих скобках указываем сообщение, которое высветится, если изображение не загрузится. Лучше написать там название файла.

В () этих скобках мы указываем название файла. Нужно быть внимательными в написании. Также, лучше если название будет без пробелов. Если что, CamelCase в помощь.


## .gitignore

Файл .gitignore нужен для того, чтобы ложить туда файлы, которые мы не хотим добавлять через add и комиттить их. Обычно это изображения, песни и тд.

Есть 3 способа игнорирования:
1. Написать название файла с указанием расширения: Switzerland.jpeg
2. *.png - игнорировать все файлы png в той папке, где идет работа
3. */.png - игнорировать все png файлы во всех файлах репозитория


## Работа с удаленными репозиториями:
# Если с локального в удаленный
1. Создаем репозиторий как обычно (через git init)
2. Сохраняем, все коммиты делаем, как обычно
3. Открываем свой аккаунт в GitHub
Создаем новый репозиторий (публичный)
4. Там будут подсказки, нам нужно скопировать что написано под ".. or push an existing repository from the command line"
5. Пишем и запускаем это в терминале
6. "Знакомимся" с GitHub, если это не было сделано раньше.
7. Все готово! Если вам нужно скинуть ссылку, то просто копируйте тот, что в зеленой кнопке "Code"

# Если с удаленного в локальный
1. Открыть терминал в VSCode и выбрать пустую папку
2. Найти нужный репозиторий с GitHub, создать Fork (сверху стоит кнопка).
- Можно добавить описание
- Можно выбрать какие ветки скопировать
3. Скопировать ссылку
4. Написать в терминале git clone ссылка_на_репозиторий
5. Создать новую ветку (желательно назвать ее своим именем/фамилией)
6. Создать файл README.md (тут инструкции), чтобы писать там заметки и тд. Или же найти этот файл, если он уже создан.
7. Добавить изменения
8. Написать git pull
9. Отправить pull request

# Заметки:
Fork + git clone - копия для локального 

Fork + git pull - merge-ит с удаленного в локальный (типа обновленная версия)

git push - отправляет с локального в удаленный

## Ссылки

## Работа с таблицами

## Цитаты

