# Модель оттока клиентов банка

## Инструменты и библиотеки:
![Python](https://img.shields.io/badge/-Python-white?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/-Pandas-white?style=flat&logo=pandas&logoColor=130754)
![seaborn](https://img.shields.io/badge/-seaborn-white?style=flat&logo=seaborn)
![matplotlib](https://img.shields.io/badge/-matplotlib-white?style=flat&logo=matplotlib)
![scikit-learn](https://img.shields.io/badge/-scikit-white?style=flat&logo=scikit-learn)
## Описание проекта:
В «Бета-Банке» наблюдается ежемесячный отток клиентов клиенты. Маркетологи считают, что сохранять текущих клиентов дешевле, чем привлекать новых. 

**Цель** — спрогнозировать, уйдёт клиент из банка в ближайшее время или нет.

**Задача исследования** — построить модель прогноза оттока с предельно большим значением F1-меры (не менее 0.59) и оценить метрику AUC-ROC.

Доступны исторические данные о поведении клиентов и расторжении договоров с банком.    

*Источник данных: [https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling](https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling)*
### Описание данных:
*Признаки:*
*	`RowNumber` — индекс строки в данных;
*	`CustomerId` — уникальный идентификатор клиента;
*	`Surname` — фамилия;
*	`CreditScore` — кредитный рейтинг;
*	`Geography` — страна проживания;
*	`Gender` — пол;
*	`Age` — возраст;
*	`Tenure` — сколько лет человек является клиентом банка;
*	`Balance` — баланс на счёте;
*	`NumOfProducts` — количество продуктов банка, используемых клиентом;
*	`HasCrCard` — наличие кредитной карты;
*	`IsActiveMember` — активность клиента;
*	`EstimatedSalary` — предполагаемая зарплата;

*Целевой признак:*
*	`Exited` — факт ухода клиента.
## Выводы:
* На этапе предобработки данных были исправлены нарушения стиля, заполнены пропуски, также данные были приведены к корректному типу;
* В ходе подготовки признаков были удалены ненужные признаки, выявлен дисбаланс классов со смещением в сторону отрицательных значений, выполнено преобразование категориальных данных в количественные с помощью метода прямого кодирования (OHE), данные разделены на обучающую, валидационную и тестовые выборки, также выполнена стандартизация данных;
* Методом обработки дисбаланса классов был выбран метод увеличения выборки (upsampling), что улучшило целевые метрики;
* Далее, были обучены и протестированы различные модели для прогнозирования оттока клиентов из «Бета-Банка». Наилучшие результаты показала модель "Случайный лес" (Random Forest) с параметрами: количество деревьев — 40 шт., глубина — 10 условий, минимальное количество объектов в узле  1 шт., обученная на сбалансированной выборке;
* В качестве показателя качества итоговой модели использовалась F1-мера, дополнительно оценивалась метрика AUC-ROC, которые составили соответственно 0.62 и 0.76 на тестовой выборке.

**Таким образом проверка обученной модели оттока на тестовой выборке подтвердила, что выбранный метод борьбы с дисбалансом классов помог нараститить целевую метрику качества F1 выше заданного в условии уровня.**