# Прогнозирование заказов такси

## Описание проекта

Служба заказа собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. Необходимо построить модель для такого предсказания.

Значение метрики RMSE на тестовой выборке должно быть не больше 48.

## Навыки и инструменты

* python
* pandas (plotting.table)
* numpy
* Time series
* statsmodels.tsa.seasonal.seasonal_decompose
* matplotlib.pyplot (patches.Rectangle)
* seaborn
* phik
* sklearn (train_test_split, cross_val_score, GridSearchCV, RandomizedSearchCV, TimeSeriesSplit, StandardScaler, OneHotEncoder, LinearRegression, Ridge, root_mean_squared_error, DecisionTreeRegressor, RandomForestRegressor, permutation_importance)
* termcolor.colored
* lightgbm
* catboost (Pool, cv, CatBoostRegressor)

## Вывод
* Построено 5 моделей. <br>
Лучший результат RMSE, равный 34.946 на тестовой выборке, у алгоритма CatBoost с гиперпараметрами {'depth': 4, 'learning_rate': 0.1, 'iteration': 350}.
* Наиболее весомые признаки: время и скользящее среднее с размером окна 3 дня (за исключением текущего); далее с большим отрывом идут дата, день недели и число заказов 7 часов назад.