# 🐾 Pet Shop – Backend API

Серверная часть для онлайн-магазина зоотоваров, созданная с использованием **Node.js**, **Express** и **MongoDB**. API поддерживает аутентификацию с ролями, управление товарами и заказами, загрузку изображений категорий и обмен данными в реальном времени через WebSocket.

---

## 🚀 Технологии

- **Node.js** + **Express.js** — RESTful API
- **MongoDB** + **Mongoose** — удалённая база данных
- **WebSocket** — обмен данными в реальном времени
- **jsonwebtoken (JWT)** — аутентификация на основе токенов
- **bcrypt** — безопасное хеширование паролей
- **multer** — загрузка файлов/изображений
- **cors** — поддержка CORS-запросов
- **dotenv** — управление переменными окружения

---

## 🔐 Аутентификация и роли

- Аутентификация на основе JWT (регистрация и вход)
- Контроль доступа по ролям:
  - `superadmin`
  - `admin`
  - `manager`
  - `user`
- Middleware:
  - `authenticate` — проверка JWT токена
  - `isSuperadmin` — ограничение доступа только для superadmin

/controllers # Бизнес-логика
/middlewares # Аутентификация, валидация, ошибки
/models # Mongoose-схемы
/routes # Маршруты API
/utils # Исключения, вспомогательные функции
/public # Загрузка изображений категорий
/temp # Временное хранилище
.env # JWT_SECRET, URI базы данных и др.

## 📌 Environment Variables (example)

```
PORT = 3000
SOCKET_PORT=5000
DATABASE_HOST=
DATABASE_NAME=
DATABASE_USER=
DATABASE_PASSWORD=
JWT_SECRET=s
DATABASE_URI=
```