# Listening Manager

Documentation for Listening Manager Backend with Node JS.

## API Documentation

| HTTP   | URI              | Description                       |
| ------ | ---------------- | --------------------------------- |
| GET    | /audios          | Retrieve all audio list           |
| GET    | /audios/{id}     | Retrieve audio specified by id    |
| POST   | /audios          | Store new audio                   |
| PUT    | /audios/{id}     | Update audio specified by id      |
| DELETE | /audios/{id}     | Delete audio specified by id      |
| GET    | /categories      | Retrieve all category list        |
| GET    | /categories/{id} | Retrieve category specified by id |
| POST   | /categories      | Store new category                |
| PUT    | /categories/{id} | Update category specified by id   |
| DELETE | /categories/{id} | Delete category specified by id   |

### Audios

#### Retrieve All Audio

```shell
GET /audios
Optional Params :
    -> page
    -> search
```

```shell
Response Body :
{
    "datas": [
        {
            "id": 3,
            "name": "IBT_VAR_1"
        },
        {
            "id": 2,
            "name": "TOEFL_VAR_7"
        }
    ],
    "total_page": 5,
    "current_page": 1
}
```

#### With Specified ID

```shell
GET /audios/{id}
```

#### Store New Audio

```shell
POST /audios

Request Body :
- audio_name : string
- audio_file : file[audio/mpeg,audio/ogg]
- categories : [] with string -> categories with JSON.stringify() with integer value
```

#### Update Audio

```shell
PUT /audios/{id}

Request Body :
- audio_name : string
- audio_file : file[audio/mpeg,audio/ogg]
- categories : [] with string -> categories with JSON.stringify() with integer value
```

#### Delete Audio

```shell
DELETE /audios/{id}
```

### Categories

#### Retrieve All Category

```shell
GET /categories
```

#### With Specified ID

```shell
GET /categories/{id}
Optional Params :
    -> page
    -> search
```

```shell
Response Body :
{
    "datas": [
        {
            "id": 3,
            "name": "IBT"
        },
        {
            "id": 2,
            "name": "TPKS"
        }
    ],
    "total_page": 3,
    "current_page": 1
}
```

#### Store New Category

```shell
POST /categories/{id}

Request Body :
- category_name
```

#### Update Category

```shell
PUT /categories/{id}

Request Body :
- category_name
```

#### Delete Category

```shell
DELETE /categories/{id}
```
