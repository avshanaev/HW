# Работа с Git
Полезные ссылки:

1.  Официальный сайт GitHub;
2.  Синтаксис Markdown.


Коммит, созданный нами, хранится в репозитарии, привязанном к конкретной папке на нашем компьютере, т.е. является локальным. Это полезно, если мы работаем над проектом самостоятельно. Однако в большинстве случаев возникает необходимость обеспечить доступ к результатам работы или доставить код на сервер, где он будет выполняться.



1.  Как подключиться к удаленному репозитарию?


Для загрузки данных в удаленный репозитарию сначала нужно к нему подключиться. В нашем примере мы используем адрес https://github.com/tutorialzine/awesome-project, однако пользователь может создать собственный удаленный репозитарий на GitHub, BitBucket или другом подобном сервисе. Это занимает некоторое время, однако в дальнейшем полностью себя оправдывает, тем более, что подобные службы имеют пошаговые инструкции для правильно выполнения нужных действий.



Для того, чтобы связать созданный нами локальный репозитарий с удаленным, выполним такую команду:

\# This is only an example. Replace the URI with your own repository address.

$ git remote add origin https://github.com/tutorialzine/awesome-project.git


Первая строка напоминает нам, что URI репозитария, который приведен в примере, нужно изменить на свой.



Иногда бывает так, что проект имеет несколько удаленных репозитариев – в таком случае каждому из них присваивается собственное имя. Главный репозитарий принято называть origin.



2.  Как отправить изменения в удаленный репозитарий?


Теперь, когда у нас в локальном репозитарии создан коммит и мы подключились к удаленному, можем отправить его на сервер. Мы это будем делать каждый раз, когда хотим обновить данные в удаленном репозитарии.



Отправка коммита осуществляется с помощью команды push, которая имеет два параметра - имя удаленного репозитория (в нашем случае origin) и ветку, в которую необходимо внести изменения (master — это ветка по умолчанию для всех репозиториев).

$ git push origin master
Counting objects: 3, done.
Writing objects: 100% (3/3), 212 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/tutorialzine/awesome-project.git

\* [new branch] master -> master


Если мы все сделали правильно, то отправленный файл hello.txt на удаленном сервере мы можем увидеть с помощью браузера. Важный момент – некоторые сервисы для отправки изменений могут требовать дополнительной аутентификации.



3.  Как клонировать удаленный репозитарий?


Если у других пользователей возникла необходимость клонировать удаленный репозитарий, они могут получить полностью работоспособную копию при помощи команды clone:

$ git clone https://github.com/tutorialzine/awesome-project.git


GitHub автоматически создаст новый локальный репозитарий в виде удаленного на собственном сервере.



Как запросить изменения с удаленного репозитария?


В случае, если другим пользователям нет необходимости делать клон удаленного репозитария, а нужно просто получить информацию об изменениях, это можно сделать с помощью команды pull:

$ git pull origin master

From https://github.com/tutorialzine/awesome-project

\* branch master -> FETCH_HEAD

Already up-to-date.


Она скачивает новые изменения. Так как мы ничего нового не вносили с тех пор, как клонировали проект, изменений, доступных к скачиванию, нет.