# Описание сущностей (таблиц)
## users (Пользователи)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| cart_id | fk(INT) | auto increment; not null; unique | корзина пользователя |
| email | VARCHAR(50) | not null | почта пользователя |
| password | VARCHAR(255) | not null | пароль пользователя |

## roles (Роли Пользователей)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| name | VARCHAR(100) | not null | название роли |


## logs (Логи)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| user_id | fk(INT) | not null | пользователь |
| message | VARCHAR(300) | not tull | сообщение |


## books (Книги)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| books_descs_id | fk(INT) | not null | описание книги |
| amount | INT | not null | количество оставшихся книг |
| status | VARCHAR(100) | not null; default(in stock) | статус |


## books_descs (Описания книг)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| name | VARCHAR(150) | not null | название книги |
| price | INT | not null | цена книги |
| description | VARCHAR(1000) | not null | описание книги |
| author_id | fk(INT) | not null | автор книги |
| pages | INT | not null | количество страниц |
| year_of_publishing | INT | not null | год издания |
| isnb | INT(13) | not null | международный стандартный книжный номер |
| genre_id | fk(INT) | not null | категория книги |


## genres (Жанры книг)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| name | VARCHAR(100) | not null | название жанра |


## carts (Корзина)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| user_id | fk(INT) | not null; unique | пользователь |
| book_id | fk(INT) | not null | книга |
| added_date | date | not null | дата добавления |


## book_images (Фото книг)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| book_id | fk(INT) | not null | книга |
| url | VARCHAR(300) | not null | путь к фото |


## reviews (Отзывы на книги)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| book_id | fk(INT) | not null | книга |
| user_id | fk(INT) | not null | пользователь |
| review | VARCHAR(300) | not null | отзыв |


## authors (Авторы)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk(INT) | auto increment; not null; unique | первичный ключ |
| name | VARCHAR(150) | not null | ФИО автора |
| date_of_birth | date | not null | дата рождения |
| biography | VARCHAR(500) | not null | биография автора |