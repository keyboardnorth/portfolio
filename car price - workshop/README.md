# Прогноз стоимости автомобиля на вторичном рынке

## Описание проекта

Проект в рамках Мастерской на [Kaggle](https://www.kaggle.com/competitions/used-cars-price-prediction-yap17/overview).

Многие знают про маркетплейсы где продаются б/у вещи, на которых есть возможность недорого купить качественную и полезную вещь. Но всегда волнует вопрос - кто и как устанавливает цену, и какие его характеристики больше всего влияют на итоговую стоимость продажи?! Вопрос становиться особо актуальным, если речь идет про дорогие товары, например про автомобили!\
Целью проекта будет разработанная модель предсказания стоимости (sellingprice) автомобиля на вторичном рынке.

## Навыки и инструменты

* python
* pandas
* numpy
* matplotlib.pyplot
* seaborn
* sklearn (rdinalEncoder, StandardScaler, OneHotEncoder, train_test_split, cross_validate, KFold, GridSearchCV, RandomizedSearchCV, RandomForestClassifier, f1_score, mean_absolute_percentage_error, DummyClassifier, LinearRegression, DecisionTreeRegressor, LogisticRegression, RandomForestRegressor, permutation_importance)
* vininfo

## Вывод

**Исследование и предобработка данных** <br><br>
Изучено 3 датасета. Отработаны пропуски, дубликаты. Добавлены новые признаки. В некоторых категориальных признаках сокращено число уникальных значений за счёт группировки. В ряде количественных признаках изменён тип данных на менее памятизатратный. Определена взаимосвязь признаков по средствам коэффициента корреляции Пирсона и диаграмм рассеяния. <br>
<br><br>
**Machine Learning**<br>
* использованные методики кодирования: Ordinal Encoding (OE), One Hot Encoding (OHE);
* масштабирование проводилось только на ОЕ для применения в линейной модели;
* проводились эксперименты с разным числом признаков, от минимального кол-ва самых влиятельных (feature_importance) до полного списка, за исключением мультиколлинеарных;
* рейтинг влиятельности признаков на целевой признак в порядке уменьшения влияния: make, body, model, country, odometer, year, trim, condition, saledate_unix, seller, state, interior, transmission, weekday, color;
* метрика для определения качества модели - Mean Absolute Percentage Error (MAPE).
<br><br>
Сводные данные по результам ML-экспериментов: <br><br>
* LinearRegression (OE), MAPE = <font color='red'>0.6863</font>;
* DecisionTreeRegressor (OE), MAPE = <font color='red'>0.2209</font> при глубине 20;
* RandomForestRegressor (OE), гиперпараметры по умолчанию, MAPE = <font color='red'>0.1795</font>;
* RandomForestRegressor (OE), RandomizedSearchCV, MAPE = <font color='red'>0.1842</font> при глубине 33 и числе деревьев 180;
* RandomForestRegressor (OE), гиперпараметры по умолчанию, только самые влиятельные признаки, MAPE = <font color='red'>0.1784</font>;
* DecissionTreeRegressor (OHE), гиперпараметры по умолчанию, MAPE = <font color='red'>0.2110</font>;
* **RandomForestRegressor (OHE), гиперпараметры по умолчанию, только самые влиятельные признаки, MAPE = <font color='red'>0.1658</font>.** <br> (модель, показавшая лучший результат)
