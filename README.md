# Документация по базовому API с поиском

## Описание

API предоставляет возможность производить поиск видео на YouTube и добавлять выбранные видео в очередь заданий.

## Методы

### GET /search

Метод для поиска видео на YouTube.

#### Параметры запроса:

- `search` - строка для поиска видео на YouTube.

#### Ответ:

- `200 OK` - список найденных видео в формате JSON.

### POST /queue

Метод для добавления выбранных видео в очередь заданий.

#### Параметры запроса:

- `url` - массив URL выбранных видео.

#### Ответ:

- `200 OK` - выбранные видео добавлены в очередь заданий.

## Примеры использования

### Поиск видео на YouTube

```
GET /search?search=котики
```

Ответ:

```
[
  {
    "id": {
      "videoId": "VIDEO_ID"
    },
    "snippet": {
      "title": "Заголовок видео",
      "thumbnails": {
        "default": {
          "url": "https://example.com/image.jpg"
        }
      }
    }
  },
  ...
]
```

### Добавление выбранных видео в очередь заданий

```
POST /queue
Content-Type: application/json

{
  "url": [
    "https://www.youtube.com/watch?v=VIDEO_ID",
    ...
  ]
}
```

Ответ:

```
200 OK
```
