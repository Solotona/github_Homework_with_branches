## GitHub Homework 2
| № | Question | Answer |
|---|:--------:|:------:|
| 1 | На локальном репозитории сделать ветки для: Postman <br> Jmeter <br> CheckLists Bug_Reports  SQL Charles Mobile_testing        | 1      |
| 2 | 2        | 2      |
| 3 | 3        | 3      |
1. На локальном репозитории сделать ветки для:
Postman
Jmeter
CheckLists
Bug_Reports
SQL
Charles
Mobile_testing
**git branch**

3. Запушить все ветки на внешний репозиторий
**git push -u origin Postman**

4. В ветке Bug_Reports сделать текстовый документ со структурой баг репорта
**git checkout Bug_report && cat > Bug_Report.txt**

5. Запушить структуру багрепорта на внешний репозиторий
**git add .
git commit -m “comment”
git push -u origin Bug_report**

6. Вмержить ветку Bag Reports в Main
**git checkout main
git merge Bug_Report**

7. Запушить main на внешний репозиторий.
**git push -u origin applePay
Затем во внешнем репозитории идем в альтернативную ветку и делаем Pull Request, чтобы смержить альтернативную ветку с main**


8. В ветке CheckLists набросать структуру чек листа.
**git checkout CheckLists
cat > Checklist.txt
1 Список   проверок
2 Статус**

9. Запушить структуру на внешний репозиторий
**git add Checklist.txt
git commit -m “Checklist.txt”**


10. На внешнем репозитории сделать Pull Request ветки CheckLists в main
**На github идем в альтернативную ветку и делаем Pull Request, чтобы смержить альтернативную ветку с main**

11. Синхронизировать Внешнюю и Локальную ветки Main
**git checkout main
git fetch
git pull**



## **==== Описание команд =====**

**git branch** - позволяет создавать, просматривать, переименовывать и удалять ветки. Она не дает возможности переключаться между ветками или выполнять слияние разветвленной истории. Именно поэтому команда git branch тесно связана с командами git checkout и git merge.

**git checkout** - позволяет перемещаться между ветками, созданными командой git branch. При переключении ветки происходит обновление файлов в рабочем каталоге в соответствии с версией, хранящейся в этой ветке, а Git начинает записывать все новые коммиты в этой ветке.

**#параметр -b** — это удобный способ сообщить системе Git, чтобы она выполнила команду git branch <новая-ветка> перед выполнением команды git checkout <новая-ветка> . По умолчанию команда git checkout -b создает новую ветку от текущего указателя HEAD.

**git merge** — объединяет несколько последовательностей коммитов в общую историю. Чаще всего команду git merge используют для объединения двух веток.
Git merge название ветки, которую мержишь (в начале становишься куда мержишь).

**git fetch** — команда в распределенной системе контроля версий Git, которая используется для скачивания изменений из удаленного или локального репозитория в свой локальный репозиторий. Польза git fetch в том, что эта команда привносит актуальность локальному репозиторию без изменения его дерева или текущей ветки.

**git pull** — используется для извлечения и загрузки содержимого из удаленного репозитория и немедленного обновления локального репозитория этим содержимым.

## **=====Лекция=====**

Пишем git branch и видим ветки (например, main).
Пишем git branch applePay и смотрим через git branch, видим что появилась ветка applePay. Так мы просто создали ветку.
Если мы хотим создать ветку и в нее перейти, то используем команду git checkout -b sumsungPay


Переходим в главную ветку git checkout main
Чтобы свичнутся (перейти) в нужную папку указываем название git checkout applePay
Открываем папку, чтобы посмотреть start .. в графическом интерфейсе

Создаем  файлик cat > transact.json (видим, что в текущей папке появился файл).
git add .
git commit -m “transact.json” (без пуша пока).

git checkout main - переходим в главную ветку и файл transact не отражается
git checkout applePay - снова переходим в альтернативную ветку и файл transact.json появляется. В этом смысл git, работа на альтернативных ветках, пока не будет принудительного смерживания с основной веткой.

Если мы хотим вмержить в основную ветку, чтобы файл transact.json появился в ветке main. В начале переходим в целевую ветку, в которую будем заливать файл - git checkout main, затем через команду git merge пишем название ветку, которую нужно вкатить: git merge applePay. Теперь мы видим, что файл есть на ветке main и applePay.

Теперь посмотрим, как резолвить конфликт.
Переходим в альтернативную ветку checkout applePay и редактируем файл nano transact.json. Коммитим изменения git commit -a -m “transact.json 2 version”
Возвращаемся в основную ветку git checkout main.
git merge applePay и видим сообщение о конфликте (Automatic merge failed; fix conflicts and then commit the result). Чтобы пофиксить конфликт, открываем файл cat transact.json и начинаем редактировать, как нам нужно, чтобы зарезолвить конфликт.

Ветки applePay и samsungPay находится пока только на локальном репозитории. Переходим на внешний репозиторий.
git push -u origin applePay.

Затем во внешнем репозитории идем в альтернативную ветку и делаем Pull Request, чтобы смержить main и ветку applePay.

Чтобы изменения отразились локально, идем в главную ветку - checkout main, проверяем, что нет файла ls -la. Делаем git fetch, чтобы проверить, что да, есть изменения. И git pull
