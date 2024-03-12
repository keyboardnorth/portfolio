# Отток клиентов

## Описание проекта

Банк начал терять клиентов. Сохранять текущих клиентов дешевле, чем привлекать новых. Необходимо построить модель прогноза оттока клиентов с предельно большим значением F1-меры (не менее 0.59).
Также требуется измерить AUC-ROC, сопоставив её значение с F1-мерой.

## Навыки и инструменты

* python
* pandas
* seaborn
* matplotlib.pyplot
* re
* numpy
* sklearn (OrdinalEncoder, StandardScaler, train_test_split, LogisticRegression, DecisionTreeClassifier, RandomForestClassifier, shuffle,  DummyClassifier, f1_score, roc_auc_score, precision_recall_curve, roc_curve, precision_score, recall_score)
* imblearn (over_sampling.SMOTE, under_sampling.RandomUnderSampler)

## Вывод

* Создана модель с метриками качества на валидационной выборке: f1 = 0.662, TPR = 0.642, FPR = 0.075, AUC-ROC = 0.874.<br> 
Таким образом модель верно детектирует 64.2% клиентов на отток.
* Модель прошла проверку на вменяемось. Сравнивалась с константной (f1=0.339) и случайной (f1=0.301).
* Проведена проверка на тестовой выборке: f1=0.593, AUC-ROC=0.855.
* Модель построена на базе алгоритма RandomForestClassifier с гиперпараметрами: depth=9, n_estimators=140, random_state=12345 с учётом порога классификации 0.33.