### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/dude-inn/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

#### Примеры запросов:

POST-запрос с токеном, добавление новой публикации в коллекцию публикаций.

`POST http://localhost:port/api/v1/posts/`

```
{ 
    "text": "string",
    "image": "string",
    "group": 0
}
```

Ответ:

```
{
    "id": 0,
    "author": "string",
    "text": "string",
    "pub_date": "2019-08-24T14:15:22Z",
    "image": "string",
    "group": 1
}
```


GET-запрос, Получение публикаций
Получить список всех публикаций. При указании параметров limit и offset выдача должна работать с пагинацией.

`GET http://127.0.0.1:8000/api/v1/posts/`

Ответ:

```
{
    "count": 123,
    "next": "http://api.example.org/accounts/?offset=400&limit=100",
    "previous": "http://api.example.org/accounts/?offset=200&limit=100",
    "results": [
    {}
]
}
```