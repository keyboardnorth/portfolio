# Определение стоимости автомобилей

## Описание проекта

Сервис по продаже автомобилей с пробегом разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля.\
В нашем распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Необходимо построить модель для определения стоимости.
Заказчику важны: качество предсказания; скорость предсказания; время обучения.

## Навыки и инструменты

* python
* pandas
* numpy
* matplotlib.pyplot
* seaborn
* random
* sklearn (train_test_split, GridSearchCV, RandomizedSearchCV, cross_val_score, StandardScaler, OneHotEncoder, OrdinalEncoder, LinearRegression, Ridge, mean_squared_error, root_mean_squared_error, DecisionTreeRegressor, RandomForestRegressor, permutation_importance)
* catboost (Pool, cv)
* lightgbm

## Вывод

1. Проведены эксперименты с 5-ю типами моделей (Linear regression,  DecisionTreeRegressor,  RandomForestRegressor, CatBoost,  LightGBM). <br> 
Лучший результат (RMSE=1549) на кросс-валидации показала модель LightGBM с гиперпараметрами depth 17, n_iter 371, learning_rate  0.05.  Время обучения и предсказания на кросс-валидации 77 секунд.
2. На тестовой выборке RMSE составляет 1519. Время обучения 28 с. Время предсказания 1 с.