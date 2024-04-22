# MLOps. Практическое задание №3 (vo_HW)

## Содержание
- [Описание](#описание)
- [Технологии](#технологии)
- [Использование](#использование)
- [Проблемы и решения](#возможные-проблемы-и-их-решения)
- [Команда проекта](#команда-проекта)

## Описание
*data_creation.py*
- Скрипт создающий Train и Test наборы данных из датасета Brilliant-Diamonds с сайта Openml.
- Сохраняет данные в директории ./test и ./train в формате .csv.
- Наборы данных делятся по 50% - 1 строка.

*data_preprocessing.py*
- Скрипт выполняющий предобработку данных.
- Категории качества огранки уменьшаются до 'low' и 'hight' и кодируются в формат 1-0.

*model_preparation.py*
- Скрипт создающий и обучающий модель машинного обучения на наборе данных из директории ./train.
- Используются библиотеки StandardScaler, MinMaxScaler, OneHotEncoder, OrdinalEncoder.
- Используется самописный класс для замены выбросов значений.
- Используется самописный класс для замены редких групп значений.
- Pipeline обработки данных и обучения модели сохраняется с помощью *pickle* в *pipeline/pipeline.pkl*

*model_testing.py*
- Скрипт проверяющий модель машинного обучения на наборе данных из директории ./test.
- Pipeline загружается с помощью *pickle* из *pipeline/pipeline.pkl*
- Сохраняет показатели работы модели в *results/results*

*main.py*
- Скрипт запуска FastAPI приложения.
- На запрос GET последовательно запускает *data_creation.py*, *data_preprocessing.py*, *model_preparation.py*, *model_testing.py* и в ответе возвращает показатели работы модели.

*Dockerfile*
- Файл с параметрами для создания docker image.

## Технологии
- [Python](https://www.python.org/)
- [Sclearn](https://scikit-learn.org/)
- [Pandas](https://pandas.pydata.org/)
- [Bash](https://ru.wikipedia.org/wiki/Bash)
- [FastAPI](https://fastapi.tiangolo.com/)

## Использование
- Установите зависимости:
```
pip install -r requirements.txt
```
- Запустите приложение:
```
bash pipeline.sh <count>
```
или
```
./pipeline.sh <count>
```
где *count* - количество наборов данных для генерации

## Команда проекта
Контакты и инструкции, как связаться с командой разработки.

- [Денис С.](tg://abc) — Developer, Орг. вопросы, оформление
