# Прогнозирование заказов такси

## Инструменты и библиотеки:
![Python](https://img.shields.io/badge/-Python-white?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/-Pandas-white?style=flat&logo=pandas&logoColor=130754)
![matplotlib](https://img.shields.io/badge/-matplotlib-white?style=flat&logo=matplotlib)
![scikit-learn](https://img.shields.io/badge/-scikit-white?style=flat&logo=scikit-learn)
![statsmodels](https://img.shields.io/badge/-statsmodels-white?style=flat&logo=statsmodels)
![LightGBM](https://img.shields.io/badge/-LightGBM-white?style=flat&logo=LightGBM)
![CatBoost](https://img.shields.io/badge/-CatBoost-white?style=flat&logo=CatBoost)
![Prophet](https://img.shields.io/badge/-Prophet-white?style=flat&logo=Prophet)
## Описание проекта:
Компания «Чётенькое такси» владеет историческими данными о заказах такси в аэропортах.

**Цель** — компании «Чётенькое такси» нужно привлекать больше водителей в период пиковой нагрузки.

**Задача исследования** — построить модель машинного обучения для прогнозирования количества заказов такси на следующий час.

### Описание данных:
*	`datetime` — дата заказа такси;
*	`num_orders` — количество заказов ;
## Выводы:
В ходе работы над проектом:

* Загружены, изучены и подготовлены данные — выполнен ресемплинг данных по часу, данные приведены к корректному типу;
* При анализе данных выявлен тренд увеличения заказов такси и внутридневная сезонность, связаная с уменьшением количества заказов такси в ночное время и ростом в дневное время;
* На этапе обучения моделей были подготовлены признаки с вручную подобранными параметрами лага и скользящего среднего, вычислены параметры бенчмарка с целью сравнения с результатами обучения; 
* Было обучено шесть различных моделей с перебором гиперпараметров, в т.ч. две модели градиентного бустинга (LightGBM и CatBoost) и модель Prophet от компании Meta (Facebook);
* Согласно скорингу по метрике RMSE, выявлена и проверена на тестовой выборке лучшая модель — CatBoost (iterations: 300, learning_rate: 0.1) с RMSE = 41.0.

**По итогу работы, были протестированы различные модели машинного обучения и выбрана целевая перспективная модель (CatBoost) для прогнозирования количества заказов такси на следующий час.**
