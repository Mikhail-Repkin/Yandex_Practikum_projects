# Исследование надёжности заёмщиков

## Инструменты и библиотеки:
![Python](https://img.shields.io/badge/-Python-white?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/-Pandas-white?style=flat&logo=pandas&logoColor=130754)
## Описание проекта:
Заказчик — кредитный отдел банка. Входные данные от банка — статистика о платёжеспособности клиентов.

**Цель исследования** — проверьте гипотезу: 

* Влияет ли семейное положение и количество детей клиента на факт погашения кредита в срок.

Результаты исследования будут учтены при построении модели кредитного скоринга — специальной системы, которая оценивает способность потенциального заёмщика вернуть кредит банку.

### Описание данных:
Согласно документации к данным:
* `children` — количество детей в семье;
* `days_employed` — общий трудовой стаж в днях;  
* `dob_years` — возраст клиента в годах;
* `education` — уровень образования клиента;
* `education_id` — идентификатор уровня образования;
* `family_status` — семейное положение;
* `family_status_id` — идентификатор семейного положения;
* `gender` — пол клиента;
* `income_type` — тип занятости;
* `debt` — имел ли задолженность по возврату кредитов;
* `total_income` — ежемесячный доход;
* `purpose` — цель получения кредита.
## Выводы:
В ходе исследования были обработаны пропущенные значения, удалены дубликаты и проведена категоризация данных для целей кредита и дохода. С помощью сводных таблиц проведена оценка гипотезы о влиянии семейного положения и количества детей клиента на факт погашения кредита в срок.

Гипотеза частично подтвердилась:
* На погашение кредита в срок скорее влияет факт наличия или отсутствия детей, а не их количество;
* Среди категорий `не женат/не замужем` и `гражданский брак` больше всего доля должников. В категории `вдовец/вдова` доля погашения в срок наиболее высокая. Доля должников в категориях `в разводе` и `женат/замужем` примерно одинакова.

Выявлены следующие инсайты:
* Клиенты с наименьшим доходом (`E`) чаще других имеют задержки по погашению кредита в срок, однако группа `D` с доходом 30–50 тыс. руб./мес. имеет самый низкий процент должников. По остальным группам показатель должников варьируется.
* Клиенты охотнее выплачивают кредит если он взят под `операции с недвижимостью` или на `проведение свадьбы`. Процент должников по кредитам на `операции с автомобилем` и `получение образования` примерно одинаков.
