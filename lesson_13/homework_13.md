1. HTTP(HuperText Transfer Protocol) - это правила, по которым браузер общается с сайтом. Ввожу адрес и браузер отправляет запрос на сервер по этим правилам, сервер отвечает.
2. HTTPS - данные шифруются. пароли и карточки не украдут, никто не подменит содержмое сайта.
3. клиент - тот, кто просит
браузер - тот, кто отвечает
клиент отправляет запрос, сервер его обрабатывает и возвращает ответ.
4. Идемпотентность - когда один и тот же запрос выполненный много раз, дает тот же результат, что и один раз

2.1.

Дан HTTP-запрос:

http
POST /api/users HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJIUzI1NiIs...
Content-Length: 58

{"name": "Иван", "email": "ivan@mail.com"}

1. POST - надо отправить данные на сервер
2. /api/users - адрес ресурса на сервере, к которому обращаемся
3. HTTP/1.1
4. Content-Type: application/json - "в теле запроса лежат данные в формате JSON"
5. Authorization: Bearer eyJhbGciOiJIUzI1NiIs... - подтверждение кто я
6. В самом низу, после пустой строки: {"name": "Иван", "email": "ivan@mail.com"}

2.2.

Дан HTTP-ответ:

http
HTTP/1.1 201 Created
Content-Type: application/json
Location: /api/users/42

{"id": 42, "name": "Иван", "email": "ivan@mail.com"}

1. 201 Created - "создано"
2. Location: /api/users/42 - где найти только что созданный ресурс
3. {"id": 42, "name": "Иван", "email": "ivan@mail.com"}

2.3.

1. Получение списка товаров:

GET /api/products HTTP/1.1
Host: example.com
Accept: application/json

2. Создание нового товара с именем "Ноутбук" и ценой 50000:

POST /api/products HTTP/1.1
Host: example.com
Content-Type: application/json
Content-Length: 52

{"name": "Ноутбук", "price": 50000}

3. Удаление товара с id=7:

DELETE /api/products/7 HTTP/1.1
Host: example.com

4. Обновление товара с id=3:

PATCH /api/products/3 HTTP/1.1
Host: example.com
Content-Type: application/json
Content-Length: 16

{"price": 45000}