##### <a name="pageup"></a>



# MANUAL_1C

+ [ШАГ 0, ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ](#Step0); ➕
+ [ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) СУЩЕСТВУЕТ на этом ПК](#Step1_1);  🟣
+ [ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) ОТСУТСТВУЕТ на этом ПК](#Step1_2); 🔘
+ [ШАГ 2, СОЗДАЕМ И ВЫПОЛНЯЕМ задачу](#Step2); 🪚


+ [ШАГ 3, ПЕРЕНОСИМ ИЗМЕНЕНИЯ (задачи в ветку копии)](#Step3);  🚡

+ [ШАГ 4, ЗАМЕНА РАБОЧИХ ФАЙЛОВ НА ИЗМЕНЕННЫЕ](#Step4); 🏁

+ [ШАГ 5, ВНЕДРЕНИЕ БЕЗ КОНФЛИКТОВ (ветки копия в ветку main)](#Step5);      🛰️
+ [СЛИЯНИЕ ВЕТОК](#Step5_1); ⚛️




_Схема разработки:_
+ Ветка main всегда содержит исключительно актуальную (рабочую) версию!
+ Любые задачи должны выполнятся в копии, по этому для нее создается ветка copy_xxxxxxxx_xx
+ Для каждой задачи должна создаватся ветке (ITTF_01) от ветки (копии)
+ Задача завершается слиянием ветки задачи (ITTF_01)  с веткой копии
+ Перед внедрением необходимо обновить ветку main до актуальной версии
+ Внедрение задачи завершается слиянием ветки копии с веткой main

+ _Обновление рабочих данных можно одним из двух способов (Загрузка из файлов ИЛИ Сравнить и объединить)_ 🏁


##### <a name="Step0"></a>	ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ [(начало)](#pageup);

# ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ ➕

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
    git commit -m "init v2.1.0.0"
    git push -u origin main
    
   _// где main - это имя первичной ветки_

   _// Если файл попал в индекс не смотря на **.gitignore** и нужно убрать его из индекса: **git rm --cached path/to/file**_
   
Таким образом мы создаем бессрочный репозиторий с веткой main в которой будет исключительно актуальная (рабочая) версия обк!




##### <a name="Step1_1"></a>	ШАГ 1,  Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **СУЩЕСТВУЕТ** на этом ПК [(начало)](#pageup);

# ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **СУЩЕСТВУЕТ** на этом ПК 🟣


1. Открываем консоль и выполняем команды:
#
    cd КорневойКаталОг_Х_Проекта
    git pull httpsRepositoryPath




##### <a name="Step1_2"></a>	ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **ОТСУТСТВУЕТ** на этом ПК [(начало)](#pageup);

# ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **ОТСУТСТВУЕТ** на этом ПК 🔘


1. Открываем консоль и выполняем команды:
#
    cd ПутьГдеБудемХранитьКаталог_Х_СПроектом
    git clone httpsRepositoryPath
    cd ИмяКлонированногоРепозитория




##### <a name="Step2"></a>	ШАГ 2, СОЗДАЕМ И ВЫПОЛНЯЕМ задачу [(начало)](#pageup);

# ШАГ 2, СОЗДАЕМ И ВЫПОЛНЯЕМ задачу 🪚

+ 🤷‍ ПЕРЕД созданием задачи:
1. _Если ветка копии существует Тогда ее надо ВЫБРАТЬ_ 🤷‍♂️ **git checkout** copy_xxxxxxxx_xx
2. _Иначе ветку копии необходимо СОЗДАТЬ и ВЫБРАТЬ ее_ 🤷‍ **git checkout -b** copy_xxxxxxxx_xx

    _и выгрузить в репозиторий удаленного сервера_ 
        
        git push -u origin copy_xxxxxxxx_xx

+ 🐤 СОЗДАНИЕ задачи:

1. Создаем для задачи ветку _(в ветке copy_xxxxxxxx_xx)_
        
        git branch ITTF_01
2. Переходим на ветку задачи:
    
        git checkout ITTF_01
3. Проверяем переход:

        git branch



##### <a name="Step2_3"></a>

+ РАБОТА НАД ЗАДАЧЕЙ: 🛠️

1. Открываем конфигурацию "Х" (или открыл обк "Х") _(в РЕЗЕРВНОЙ копии)_
2. 🩹 Вносим изменения

_Первое изменение которое можно внести и зафиксировать это смена версии (обработки) "x.x.x.1"_

_Когда решили что пора сохранить изменения в сис. контроля версий ЛОКАЛЬНО:_ ◘

3. Выполнил команду   **"Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"**

_выгружаем с заменой текущих файлов (перезаписываем, обязательно при этом должна быть выбрана ветка задачи!)_
#
    git add .
    git status
    git commit -m "some comment"

  **Повторяем с шага №2** 🩹


_Когда решили что пора сохранить изменения в сис. контроля версий УДАЛЕННО_ ✔️
#   
    git push -u origin ITTF_01




##### <a name="Step3"></a>  ПЕРЕНОСИМ ИЗМЕНЕНИЯ _(задачи в ветку копии)_ [(начало)](#pageup);

# ШАГ 3, ПЕРЕНОСИМ ИЗМЕНЕНИЯ _(задачи в ветку копии)_ 🚡


1. Переходим на ветку копии: git checkout copy_xxxxxxxx_xx
2. Выполняем слияние ветки копия с веткой задачи: git merge ITTF_01

_По необходимости коммитим и пушим на удаленный сервер ветку copy_xxxxxxxx_xx_




##### <a name="Step4"></a> ШАГ 4, ЗАМЕНА РАБОЧИХ ФАЙЛОВ НА ИЗМЕНЕННЫЕ [(начало)](#pageup);

# ШАГ 4, ЗАМЕНА РАБОЧИХ ФАЙЛОВ НА ИЗМЕНЕННЫЕ: 🏁

1. Через конфигуратор выполнил сравнить и объединить (для устранения конфликтов)
    
        Если Конфликт Тогда
            ОБЪЕДИНЯЕМ (merge) ветку копии с веткой задач
            Удаляем ветки задач (git branch -d ITTF_xx)
            
            ОБЪЕДИНЯЕМ (merge) ветку main с веткой копии
            Удаляем ветки копии (git branch -d copy_xxxxxxxx_xx)
            
            РЕШАЕМ конфликт через конфигуратор (оставляем нужное и удаляем не нужное)
            Результатом решения конфликта через конфигуратор будет новая версия обк!

            Новый обк готов заменить текущий рабочий обк!
            
            АКТУАЛИЗИРУЕМ данные (добавлением нового обк) в сис. контроля версий
            git fetch
            git pull
            
            "Выгружаем в файлы" новую версию (которая получилась после решения конфликта)
            в репозиторий текущего проекта (в единственную ветку main)
            
            git add .
            git commit -m "ITFC_xxxxxxxx_xx"
            git push -u origin main
        ИНАЧЕ
            ВЫПОЛНЯЕМ ШАГ 5 (ВНЕДРЕНИЕ БЕЗ КОНФЛИКТОВ 🛰️)
            
            


##### <a name="Step5"></a>	ШАГ 5, ВНЕДРЕНИЕ БЕЗ КОНФЛИКТОВ _(ветки копия в ветку main)_ [(начало)](#pageup);

# ШАГ 5, ВНЕДРЕНИЕ БЕЗ КОНФЛИКТОВ _(ветки копия в ветку main)_ 🛰️

Обновляем ветку main до актуальных данных:

1. Переходим на ветку main: git checkout main
2. Открываем конфигурацию "Х" (или открыл обк "Х") с актуальными данными (РАБОЧАЯ база)
3. Выполнил команду   **"Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"**
    _где каталОг для выгружаемых файлов это ЛокальныйРепозиторийПроекта_
    _(сохраняем с заменой текущих файлов). Командой git status можно увидеть изменения_
#
    git add .
    git commit -m "update_to_current_data"
    git push -u origin main



##### <a name="Step5_1"></a>	**СЛИЯНИЕ ВЕТОК** main и copy_xxxxxxxx_xx [(начало)](#pageup);

⚛️

_убедитесь что ветка copy_xxxxxxxx_xx слита с ветками выполненых задач и готова завершить свое существование_

1. Переходим на принимающую ветку:                                      **git checkout main**
2. Что бы получить последние коммиты ветки:                             **git fetch**
3. Затем убедитесь, что в ветке main содержатся последние изменения:  **git pull**
#
    git merge** copy_xxxxxxxx_xx
    git commit -m "merge ITTF_01_ITTF_02"
    git push -u origin main
   _// где "copy_xxxxxxxx_xx" - это название ветки-источник_
   _// где main - это имя первичной ветки._
   
    git fetch
    git pull
4. Открываем рабочую базу (заблокированную нами) и _"Загрузить конфигурацию из файлов/ Загрузить из файлов"_


[(начало)](#pageup);

4. Удаляем вспомогательную ветку созданную для актуализации данных: 🙈

        git branch -d copy_xxxxxxxx_xx




# Добплнительно:
    На удаленный сервер выгружаются из локального репозитория ИСКЛЮЧИТЕЛЬНО
    те ветки из которых была выполнена команда push. Что бы выгрузить две
    ветки необходимо в каждой из них выполнить команду push
    (иначе ветка останется исключительно в текущем локальном репозитории)
    
    С какой ветки выполняется команда создать новую ветку - с той ветки
    начинается новое ответвление (копируется именно та ветка С которой выполнена команда!)
    
    После push (особенно main ветки) лучше убедится что push выполнился,
    а то у меня была ситуация что commit остался в локальном репозитории! 🤡



[(начало)](#pageup);
