# Классификация персонажей из мультсериала "Симпсоны"

Цель проекта - классифицировать персонажей из мультсериала "Симпсоны" используя машинное обучение. Датасет использующийся в этом проекта взят с сайта https://www.kaggle.com/datasets/alexattia/the-simpsons-characters-dataset/data

# Аугментация

В связи с нехваткой изображений некоторых классов необходима аугментация. В результате разброс между количеством изображений в классах будет уменьшен. В ходе аугментации происходят следующие преобразования:
1) iaa.Flipud(1.0) - Вертикальное зеркальное отражение;
2) iaa.Rotate((-25, 25)) - поворот на угол от -25 до 25 градусов
3) iaa.AdditiveGaussianNoise(loc=0, scale=(10, 20)) - добавление шума силы от 10 до 20;
4) iaa.Multiply((1.0, 1.5)) - изменение яркости от 10% до 50% (значения от 1.1 до 1.5)

# Обучение, валидация и тестирование

1) Аугментация train датасета
3) Разбиение train датасета на val и train в отношении 1 к 4
4) Создание train_loader и val_loader
5) Создание сверточной модели нейросети
6) Обучение модели и валидация
7) Тестирование модели на test данных

# Библиотеки

Для загрузки датасета необходимо установить библиотеку opendatasets
Она также указана в файле `requirements.txt`
