# Навигация


* **pwd** (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;


* **ls** (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;


* **ls -a** — покажи также скрытые файлы и папки, названия которых начинаются с символа .;


* **cd first-project** (от англ. change directory, «сменить директорию») — перейди в папку **first-project**;


* **cd first-project/html** — перейди в папку html, которая находится в папке **first-project**;


* **cd ..** — перейди на уровень выше, в родительскую папку;


* **cd** ~ — перейди в домашнюю директорию (/Users/Username);


* **cd /** — перейди в корневую директорию.


# Работа с файлами и папками


## Создание


* **touch index.html** (англ. touch, «коснуться») — создай файл **index.html** в текущей папке;


* **ouch index.html style.css script.js** — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;


* **mkdir second-project** (от англ. make directory, «создать директорию») — создай папку с именем **second-project** в текущей папке.


## Копирование и перемещение
* **cp file.txt ~/my-dir** (от англ. copy, «копировать») — скопируй файл в другое место;


* **mv file.txt ~/my-dir** (от англ. move, «переместить») — перемести файл или папку в другое место.


## Чтение


* **cat file.txt** (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла **file.txt**.


## Удаление


* **rm about.html** (от англ. remove, «удалить») — удали файл **about.html**;


* **rmdir images** (от англ. remove directory, «удалить директорию») — удали папку **images**;


* **rm -r second-project** (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку **second-project** и всё, что она содержит.


# Первоначальная настройка


Настройка информации о пользователе для всех локальных репозиториев


```
$ git config --global user.name "[имя]"
```


Устанавливает имя, которое будет отображаться в поле автора у выполняемых вами коммитов


```
$ git config --global user.email "[адрес электронной почты]"
```

Устанавливает адрес электронной почты, который будет отображаться в информации о выполняемых вами коммитах


# Создание репозитория


Создание нового репозитория или получение его по существующему URL-адресу


```
$ git init [название проекта]
```

# Внесение изменений


Просмотр изменений и создание коммитов (фиксация изменений)


```
$ git status
```


Перечисляет все новые или изменённые файлы, которые нуждаются в фиксации


```
$ git diff
```


Показывает различия по внесённым изменениям в ещё не проиндексированных файлах


```
$ git add [файл]
```


Индексирует указанный файл для последующего коммита


```
$ git diff --staged
```


Показывает различия между проиндексированной и последней зафиксированной версиями файлов


```
$ git reset [файл]
```


Отменяет индексацию указанного файла, при этом сохраняет его содержимое


```
$ git commit -m "[сообщение с описанием]"
```


# Операции с файлами


Перемещение и удаление версий файлов репозитория


```
$ git rm [файл]
```


Удаляет конкретный файл из рабочей директории и индексирует его удаление


```
$ git mv [оригинальный файл] [новое имя]
```


# Просмотр истории


Просмотр и изучение истории изменений файлов проекта


```
$ git log
```


История коммитов для текущей ветки


```
$ git log --follow [файл]
```


История изменений конкретного файла, включая его переименование


```
$ git diff [первая ветка]...[вторая ветка]
```


Показывает разницу между содержанием коммитов двух веток


```
$ git show [коммит]
```


# Откат коммитов


Удаление ошибок и корректировка созданной истории


```
$ git reset [коммит]
```


Отменяет все коммиты после заданного, оставляя все изменения в рабочей директории


```
$ git reset --hard [коммит]
```


# Синхронизация с удалённым репозиторием


Регистрация удалённого репозитория и обмен изменениями


```
$ git fetch [удалённый репозиторий]
```


Скачивает всю историю из удалённого репозитория


```
$ git merge [удалённый репозиторий]/[ветка]
```


Вносит изменения из ветки удалённого репозитория в текущую ветку локального репозитория


```
$ git push [удалённый репозиторий] [ветка]
```


Загружает все изменения локальной ветки в удалённый репозиторий


```
$ git pull
```


# Хеш — идентификатор коммита


**Хеширование** (от англ. hash, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их «отпечаток» (англ. fingerprint).


**Информация о коммите** — это набор данных: когда был сделан коммит, содержимое файлов в репозитории на момент коммита и ссылка на предыдущий, или родительский (англ. parent), коммит.


Git хеширует (преобразует) информацию о коммите с помощью алгоритма SHA-1 (от англ. Secure Hash Algorithm — «безопасный алгоритм хеширования») и получает для каждого коммита свой уникальный хеш — результат хеширования.
Обычно хеш — это короткая (40 символов в случае SHA-1) строка, которая состоит из цифр 0—9 и латинских букв A—F (неважно, заглавных или строчных). Она обладает следующими важными свойствами:


* если хеш получить дважды для одного и того же набора входных данных, то результат будет гарантированно одинаковый;


* если хоть что-то в исходных данных поменяется (хотя бы один символ), то хеш тоже изменится (причём сильно).


Все хеши и таблицу **хеш → информация о коммите** Git сохраняет в служебные файлы. Они находятся в скрытой папке .git в репозитории проекта.







































