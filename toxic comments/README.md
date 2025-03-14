# Распознавание токсичных комментариев

## Описание проекта

Интернет-магазин запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию.

Необходимо обучить модель классифицировать комментарии на позитивные и негативные.\
Есть в наличии набор данных с разметкой о токсичности правок. В файле `toxic_comments.csv` столбец *text* содержит комментарий, а *toxic* — целевой признак.

Требуется построить модель со значением метрики качества *F1* не меньше 0.75.

## Навыки и инструменты

* python
* pandas
* numpy
* torch
* transformers (Bert)
* tqdm.notebook
* wordcloud
* spacy
* math.ceil
* imblearn (over_sampling.SMOTE, under_sampling.RandomUnderSampler)
* sklearn (TfidfVectorizer, train_test_split, LogisticRegression, f1_score, DecisionTreeClassifier, RandomForestClassifier)
* lightgbm
* catboost (CatBoostClassifier, Pool)
* re
* matplotlib.pyplot
* termcolor.colored

## Вывод

* Исходный датасет состоит из размеченного набора комментариев - 152292 шт.
* Сильный дисбаланс: нетоксичных твитов в 10 раз больше чем токсичных. Дубликатов нет.
* Проверено 3 варианта кодирования: TF-IDF (после лемматизации и очистки от стоп-слов), Bert и Bert_toxic.
* Протестировано 5 типов ML-алгоритмов (LogisticRegression, DecisionTreeClassifier, RandomForestClassifier, LightGBM, CatBoostClassifier).
* Значительно лучшие результаты показали модели закодированные на предобученном алгоритме Bert_toxic, что говорит о важности правильного выбора предобученной модели Bert в задачах NLP.
* Лучшая модель  LogisticRegression (Bert_toxic) c алгоритмом оптимизации lbfgs на тестовой выборке дала результат F1 = 0.9431. <br> Кроме того данная линейная модель является самой быстрой, что важно для комфортного пользования сайтом магазина.
