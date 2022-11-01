# My git instruction

* *git init*   - команда, инициализирующая репозиторий в текущей папке;
* *git status* - команда отображает статус изменений;
* *git add* - команда добавления изменений;
* *git log* - команда выводит список сохранений;
>Для перемещения по списку сохранений, отображаемых командой **git log**, используй стрелки *"вверх"/"вниз"*. Для полного выхода из меню нажми на клавишу **"Q"**.

* *git checkout* - команда переключения между сохраненными версиями;
* *git checkout master* - команда возврата к самому последнему сохранению;
* *git commit - m""* - команда фиксации изменений, работает в связке с git add;
* Это [ссылка](https://texterra.ru/blog/ischerpyvayushchaya-shpargalka-po-sintaksisu-razmetki-markdown-na-zametku-avtoram-veb-razrabotchikam.html "с заголовком") на описание языка разметки MarkDown с заголовком (тайтлом);
> Не забывай сохранять изменения через сочетания клавишь **Ctrl+S**

>Здесь [шпаргалка](
https://training.github.com/downloads/ru/github-git-cheat-sheet/) по программе **GIT**
___

Шпаргалка GIT
![Шпаргалка GIT](ShpargalkaGIT.jpg)

Шпаргалка MarkDown
![Шпаргалка MarkDown](ShpargalkaMarkDown.jpg)
___
___

| Команда | Действие 
|---------| ---------|
| git commit --amend - m""| Изменение комментария к сохранению |
|clear| Очищает окно терминала|
|git diff| Отображает изменения относительно последнего сохранения, показывает добавленные и удаленные строки, детальное отображение изменений
|git status| Отображает статус изменения целой папки/файла|


# Работа с ветвлением 
### **Проблема**
 Сообщение HEAD detached from 821d70f информиует о том, что текущая рабочая ветка отделилась от главной "main". Это видно при вызове *git log*.
Пример: 

commit ebd861945f1afacf54bec269b7f2c791f2b2be0f (HEAD)
commit 821d70ffca37f1c263e8623ae57ae183e170bd88 (main)

### **Решение**
1. Переходим в главную ветку git checkout main
2. Создаем новую ветку:

*git branch name_new_branch number_commit_HEAD*

Пример: 

git branch lost_branch ebd861945f1afacf54bec269b7f2c791f2b2be0f

3. Производим слияние git merge name_new_branch

Пример: git merge lost_branch

4. Та-дам! Магия произошла: HEAD -> main, и все данные теперь в основной ветке.

5. Можно удалить ветку lost_branch командой

 *git branch -d lost_branch*

 # Цвета радуги
 * Красный,
 * оранжевый,
 * желтый,
 * зеленый,
 * голубой,
 * синий,
 * фиолетовый.
 
 >Для запоминания цветов радуги необходимо запомнить фразу:  
 >*Каждый
 охотник
 желает
 знать,
 где
 сидит
 фазан*.
 
 # Работа с удаленным репозиторием
 ## Отправка изменений в удаленный репозиторий

* Создаем аккаунт на Github
* Создаем новый репозиторий
* Используем инструкцию Github. Пример: 
> …or push an existing repository from the command line
>
>git remote add origin https://github.com/ELENA-MALINOVSKAYA/GIT_TUTORIAL.git
>
>git branch -M main
>
>git push -u origin main

## Синхронизация локального репозитория с удаленным репозиторием

* на терминале локального репозитория вводим команду

>git pull origin main

## Клонирование чужого репозитория на локальный компьютер и свой удаленный репозиторий github

* Создаем папку на компьютере
* через cmd/VSC/PowerShell/Git Bash и др вводим команду

> git clone <url репозитория>

>**ВАЖНО!!! git clone уже предполагает (включает в себя) git init и многое другое.** 

* Далее вызываем команду *git status*
* В случае возникновения следующего сообщения, как на примере ниже, вам следует поменять директорию клонированного репозитория.

*PS C:\GIT\GIT_CLONE> git status
fatal: not a git repository (or any of the parent directories): .git*

* Команда **"ls"** отображает список объектов в текущей директории
* Команда **"cd имя.папки/файла"** меняет директорию на указанную.
* Вновь проверяем git status. Если мы попали в папку репозитория, то мы увидим информацию о текущей ветке.

Пример:

>*On branch master
Your branch is up to date with 'origin/master'.*
>
>*nothing to commit, working tree clean*

* Далее, если получаем  ошибку 

  __*remote origin already exists.*__ 

после команды с github 

**git remote add origin** https://github.com/ELENA-MALINOVSKAYA/GB_CLONE_2.git  ,

тогда вводим команду 

>**git remote set-url origin** https://github.com/ELENA-MALINOVSKAYA/GB_CLONE_2.git

* Далее вводим команду git branch. Проверяем находимся ли мы на главной ветке и название  главной ветки: main или master.
* вводим команду 

**git push -u origin master**
* Все готово: клонированный чужой репозиторий у вас на github

# LIFEHACK
Команда **git log --oneline --all** отображает в сокращенной форме все коммиты во всех ветвях с указанием на конкретную ветку.