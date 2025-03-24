# Домашнее задание к занятию «Базы данных» Федоров Дмитрий

### Инструкция по выполнению домашнего задания

<details>


1. Сделайте fork [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и ваши фамилию и имя;
   - в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
   - для корректного добавления скриншотов воспользуйтесь инструкцией [«Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
   - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`).
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания.
</details>


---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;

<details>
<summary>Ответ</summary>

* ФИО сотрудника  - фамилия, имя и отчество сотрудника
* Оклад  - заработная плата сотрудника
* Должность  - занимаемая должность сотрудником
* Тип подразделения - отдел в котором работает сотрудник
* Структурное подразделение - принадлежность учреждению
* Дата найма - дата найма сотрудника
* Адрес филиала - местонахождение филиала
* Проект на который назначен - наименование проeкта на который назначен сотрудник

</details>

- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

<details>
<summary>Ответ</summary>

* ФИО сотрудника  -  строковый (varchar)
* Оклад  - числовой (decimal/numeric)
* Должность  - строковый (varchar)
* Тип подразделения - строковый (varchar)
* Структурное подразделение - строковый (varchar)
* Дата найма - дата и время (tinyint)
* Адрес филиала - местонахождение филиала (varchar)
* Проект на который назначен - строковый (varchar)

</details>


Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

<details>
<summary>Ответ</summary>

employees (
- id_employee, int, not null, auto_increment, primary_key
- last_name, varchar(50), not null
- first_name, varchar(50), not null
- surname, varchar(50)
- salary, foreign_key
- rank, foreign_key
- subdivision, foreign_key
- structural_division, foreign_key
- hired_since, date, not null
- office, foreign_key
- project, foreign_key
)
---

salary (
- id_salary, int, not null, auto_increment, primary_key
- salary, real, not null
)
---

ranks (
- id_rank, int, not null, auto_increment, primary_key
- rank, varchar(100), not null
)
---

subdivisions (
- id_subdivision, int, not null, auto_increment, primary_key
- subdivision, varchar(100), not null
- type_of_subdivision, foreign_key
- office, foreign_key
)
---

type_of_subdivision (
- id_of_type, int, not null, auto_increment, primary_key
- type
)
---

offices (
- id_office, int, not null, auto_increment, primary_key
- office, varchar(200), not null
)
---

projects (
- id_project, int, not null, auto_increment, primary_key
- project, varchar(100), not null
)
</details>

------
