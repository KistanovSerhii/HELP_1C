# MANUAL_1C

+ [ШАГ 0, ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ](#Step0);
+ [ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) СУЩЕСТВУЕТ на этом ПК](#Step1_1);
+ [ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) ОТСУТСТВУЕТ на этом ПК](#Step1_2);
+ [ШАГ 2, ПЕРЕД НАЧАЛОМ/КОНЦОМ ЛЮБОЙ ЗАДАЧИ](#Step2);
+ [СЛИЯНИЕ ВЕТОК](#Step2_1);
+ [ШАГ 3, ИЗМЕНЕНИЯ ДАННЫХ](#Step3);
+ [ШАГ 4, ВНЕДРЯЕМ В РАБОЧИЙ объект](#Step4);


# ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ
##### <a name="Step0"></a>	ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ

1. **Создаем репозиторий** "X" на удаленном сервере github

    _**ВАЖНО** при создании репозитория, выбрать: **Add .gitignore**_
    _указав template: **Scheme** (какой шаблон неважно)_

2. Редактируем файл .gitignore: очищаем, добавляем **ConfigDumpInfo.xml**, сохраняем

3. _Открываем консоль и выполняем команды:_
#    
    cd ПутьГдеБудемХранитьКаталог_Х_СПроектом
    git clone httpsRepositoryPath
    cd ИмяКлонированногоРепозитория

4. Создаем актуальную _РЕЗЕРВНУЮ копию_ и работаем в дальнейшем с ней
5. Открываем (в) конфигуратор (торе) актуальную _РЕЗЕРВНУЮ копию_
6. Выполнил команду   **"Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"**

   _где каталОг для выгружаемых файлов это ЛокальныйКаталог-КлонированыйРепозиторий_

7. Открываем консоль и выполняем команды:
#
    git add .
    git commit -m "init nameObj_X"
    git push -u origin main
    
   _// где main - это имя первичной ветки_

   _// Если файл попал в индекс не смотря на **.gitignore** и нужно убрать его из индекса: **git rm --cached path/to/file**_



# ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **СУЩЕСТВУЕТ** на этом ПК
##### <a name="Step1_1"></a>	ШАГ 1,  Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **СУЩЕСТВУЕТ** на этом ПК

1. Открываем консоль и выполняем команды:
#
    cd КорневойКаталОг_Х_Проекта
    git pull httpsRepositoryPath



# ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **ОТСУТСТВУЕТ** на этом ПК
##### <a name="Step1_2"></a>	ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **ОТСУТСТВУЕТ** на этом ПК

1. Открываем консоль и выполняем команды:
#
    cd ПутьГдеБудемХранитьКаталог_Х_СПроектом
    git clone httpsRepositoryPath
    cd ИмяКлонированногоРепозитория



# ШАГ 2, ПЕРЕД НАЧАЛОМ/КОНЦОМ ВЫПОЛНЕНИЯ ЛЮБОЙ ЗАДАЧИ
##### <a name="Step2"></a>	ШАГ 2, ПЕРЕД ВЫПОЛНЕНИЕМ ЛЮБОЙ ЗАДАЧИ _(актуализируем данные)_

_(1:Начало, выполняется только один раз перед началом новой задачи или 2:Конец, перед внедрением выполненой задачи)_

1. Добавляем ветку:     **git branch**     update_to_current_data
2. Переходим в ветку:   **git checkout**   update_to_current_data
2. Открываем конфигурацию    "Х" (или открыл обк "Х") с актуальными данными (РАБОЧАЯ база)
3. Выполнил команду   **"Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"**
    _где каталОг для выгружаемых файлов это ЛокальныйРепозиторийПроекта_
    _(сохраняем с заменой текущих файлов). Командой git status можно увидеть изменения_
#
    git add .
    git commit -m "update_to_current_data"
    git push -u origin update_to_current_data



**СЛИЯНИЕ ВЕТОК**
##### <a name="Step2_1"></a>	СЛИЯНИЕ ВЕТОК _(вливаем в главную ветку данные ветки с новыми данными)_

1. Переходим на принимающую ветку   **git checkout main**   _// где main - это  прин. ветка_
2. Выполните команду   **git fetch**, чтобы получить из него последние коммиты
3. Затем убедитесь, что в ветке main также содержатся последние изменения   **git pull**
#
    git merge** update_to_current_data
    git commit -m "merge update_to_current_data
    git push -u origin main 
   _// где "update_to_current_data" - это название ветки-источник_
   _// где main - это имя первичной ветки._

7. Удаляем вспомогательную ветку созданную для актуализации данных:   **git branch -d** update_to_current_data



# ШАГ 3, ИЗМЕНЕНИЯ ДАННЫХ
##### <a name="Step3"></a>	ШАГ 3, ИЗМЕНЕНИЯ ДАННЫХ (ВСЕГДА В НОВОЙ ВЕТКИ!)

1. Создаем ветку для выполнения "задачи":   **git branch**   _ITTF_01_
2. Переходим на ветку задачи:               **git checkout** _ITTF_01_
3. Проверяем переход:                       **git branch**

4. Открываем конфигурацию    "Х" (или открыл обк "Х") _(РЕЗЕРВНУЮ копию)_

5. Вносим изменения
6. Выполнил команду   **"Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"**
#
    git add .
    git status
    git commit -m "some comment"

∞ **Повторяем с шага №5**


# Выгрузить ветку
1. Когда захотим выгрузить ветку на удаленный сервер:
#    
    **git push -u origin** _ITTF_01_



# ШАГ 4, ВНЕДРЕНИЕ _(конец задачи)_
##### <a name="Step4"></a>  ВНЕДРЯЕМ В РАБОЧИЙ объект

1. БЛОКИРУЕМ рабочий **объект/конфигуратор** до окончания процесса внедрения
2. ВЫПОЛНЯЕМ ШАГ №2 (актуализируем данные)
3. ВЫПОЛНЯЕМ **СЛИЯНИЕ ВЕТОК** main с _Веткой текущей задачи_



# Добплнительно:
    На удаленный сервер выгружаются из локального репозитория ИСКЛЮЧИТЕЛЬНО
    те ветки из которых была выполнена команда push. Что бы выгрузить две
    ветки необходимо в каждой из них выполнить команду push
    (иначе ветка останется исключительно в текущем локальном репозитории)
