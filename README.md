## API для дипломного проекта NewsExplorer

#### NewsExplorer - сервис поиска новостей. Можно сохранить новости в личном кабинете.

###  Как работает:
- Cхемы и модели ресурсов API
  - Поля схемы user:
    - email — почта пользователя, по которой он регистрируется. Это обязательное поле, уникальное для каждого пользователя. Валидируется на соответствие схеме электронной почты.
    - password — хеш пароля. Обязательное поле-строка. Поведение по умолчанию, чтобы база данных не возвращала это поле
    - name — имя пользователя, например: Александр или Мария. Это обязательное поле-строка от 2 до 30 символов.
  - Поля схемы article
    - keyword — ключевое слово, по которому статью нашли. Обязательное поле-строка.
    - title — заголовок статьи. Обязательное поле-строка.
    - text — текст статьи. Обязательное поле-строка.
    - date — дата статьи. Обязательное поле-строка.
    - source — источник статьи. Обязательное поле-строка.
    - link — ссылка на статью. Обязательное поле-строка. Должно быть URL-адресом.
    - image — ссылка на иллюстрацию к статье. Обязательное поле-строка. Должно быть URL-адресом.
    - owner — _id пользователя, сохранившего статью. Поведение по умолчанию, чтобы база данных не возвращала это поле.
- Роуты с авторизацией: 
  - GET /users/me (возвращает информацию о пользователе (email и имя));
  - GET /articles (возвращает все сохранённые пользователем статьи);
  - POST /articles (создаёт статью с переданными в теле: keyword, title, text, date, source, link и image);
  - DELETE /articles/articleId (удаляет сохранённую статью  по _id);
- Роуты без авторизации:
  - POST /signup (создаёт пользователя с переданными в теле: email, password и name);
  - POST /signin (проверяет переданные в теле почту и пароль и возвращает JWT);

## Запуск:

- npm run start -- версия для продакшн
- npm run dev -- запуск в режиме разработки

## Ссылки:
- проект на gh-pages: https://elensmith.github.io/diploma-NewsExplorer-frontend
- фронт и бэк на одном сервере https://www.elena-k.tk/ 

- фронтенд тут: https://github.com/Elensmith/diploma-NewsExplorer-frontend


#### version 1.0.7
