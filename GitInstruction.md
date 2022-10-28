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

<<<<<<< HEAD
 >Каждый
 охотник
 желает
 знать
 где
 сидит
 фазан
 
 >Красный,
 оранжевый,
 желтый,
 зеленый,
 голубой,
 синий.

 Merge branch 'Number_2_A' into Number_2
 
=======
 > RED, ORANGE, YELLOW, GREEN, BLUE, INDIGO, VIOLET.
>>>>>>> Number_2_B
