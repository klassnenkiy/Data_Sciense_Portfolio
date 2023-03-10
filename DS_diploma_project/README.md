# Задача

Оператор связи «Ниединогоразрыва.ком» хочет научиться прогнозировать отток клиентов. Если выяснится, что пользователь планирует уйти, ему будут предложены промокоды и специальные условия. Команда оператора собрала персональные данные о некоторых клиентах, информацию об их тарифах и договорах.

# Навыки и инструменты
- Pandas 
- Sklearn 
- Seaborn 
- Lightgbm 
- Matplotlib 
- Numpy

# Выводы

В процессе предобработки данных:

- изменили стиль наименования столбцов 
- поменяли типы данных в столбцах total_charges, begin_date и end_date
- заполнили пропуски в total_charges на montly_charges
- добавили столбец с классами для целевого признака и дюрацией

Далее объединили исходные данные, обработали пропуски. Провели исследование и общую подготовку данных. 

Выяснили, что большинство ушедших клиентов

- выбирали помесячную оплату
- выбирали выставление счёта на электронную почту
- выбирали электронный чек как средство оплаты
- были как женщинами так и мужчинами
- чаще не имели супруга/партнера
- чаще использовали оптоволокно при подключении к интернету
- реже пользовались технической поддержкой

Также определили что больше всего уходят клиенты со средним чеком ~ 70-105. Чем больше дюрация сотрудничества тем меньше веротяность ухода клиента.

Далее обработали и подготовили данные для моделей. Применили скалирование для количественных признаков и OHE для категориальных.

Взяли три модели RandomForestClassifier, LGBMClassifier и CatBoostClassifier. Подобрали подобрали гиперпараметры и обучили.

По итогу, наилучший результат показала модель **CatBoostClassifier**. 

Протестировали лучшую модель и расчитали метрики. **ROC-AUC=0.9249 и Accuracy=0.8790**

Наконец, провели анализ важности признаков  для лучшей модели. Наиболее важные признаки - days_duration и monthly_charges

Все пункты первоначального плана были выполнены.

- Загрузка данных и их начальная предобработка (типы, пропуски, дубликаты)
- Объединение/склейка данных
- EDA - Исследовательский анализ данных (посмотреть зависимости, вузализация, выводы)
- Провести подготовку данных к моделированию (исследовать баланс классов, исключение признаков, нормализовать данные)
- Выбор моделей машинного обучения (RandomForestClassifier, LGBMClassifier и CatBoostClassifier)
- Обучение моделей
- Выбрать лучшую модель (CatBoostClassifier)
- Тестирование (ROC-AUC=0.9249 и Accuracy=0.8790)
- Общий вывод/Составление отчета
