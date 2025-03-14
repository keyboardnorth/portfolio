# Определение возраста человека по фотографии

## Описание проекта

Сетевой супермаркет внедряет систему компьютерного зрения для обработки фотографий покупателей. Фотофиксация в прикассовой зоне поможет определять возраст клиентов, чтобы:

* Анализировать покупки и предлагать товары, которые могут заинтересовать покупателей этой возрастной группы;
* Контролировать добросовестность кассиров при продаже алкоголя.

Необходимо построить модель (свёрточную нейронную сеть), которая по фотографии определит приблизительный возраст человека.<br>
В нашем распоряжении набор фотографий людей и датасет с указанием названия изображения и возраста.

Требуется получить значения MAE на тестовой выборке не больше 8.

## Навыки и инструменты

* python
* numpy
* pandas/plotting.table
* PIL.Image
* tensorflow.keras (ImageDataGenerator, layers, models, optimizers, applications.resnet)
* matplotlib.pyplot
* seaborn

## Вывод

Построена модель на основе свёрточной нейронной сети ResNet50. <br>
Лучшее значение MAE = 6.5763 достигнуто на тестовой выборке  на 10-ой эпохе с оптимизатором Adam при learning_rate 0.0001. В батче по 32 объекта.