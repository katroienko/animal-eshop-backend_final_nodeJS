# 🐾 Pet Shop – Backend API

A backend service for a pet shop built with **Node.js**, **Express**, and **MongoDB**. This API supports authentication with roles, product and order management, category image uploads, and real-time updates via WebSocket.

---

## 🚀 Tech Stack

- **Node.js** + **Express.js** — RESTful API
- **MongoDB** + **Mongoose** — remote database
- **WebSocket** — real-time communication
- **jsonwebtoken (JWT)** — token-based authentication
- **bcrypt** — secure password hashing
- **multer** — file/image upload
- **cors** — cross-origin requests
- **dotenv** — environment variable management

---

## 🔐 Authentication & Roles

- JWT-based login and registration
- Role-based access control:
  - `superadmin`
  - `admin`
  - `manager`
  - `user`
- Middlewares:
  - `authenticate` — validates JWT
  - `isSuperadmin` — restricts access to superadmins

---

## 📁 API Endpoints

### `POST /api/auth`
- User registration & login
- Token generation

### `GET /api/users`
- Manage users (admin-only)

### `GET /api/categories`
- Create, update, delete categories
- Upload image to `public/`
- Uses `multer` for image upload

### `GET /api/products`
- Product CRUD operations

### `GET /api/orders`
- Order processing

---

## 🛡 Error Handling

- `notFoundHandler` — for 404 (route not found)
- `errorHandler` — for internal server errors
- `HttpException` — custom utility for structured error responses

---

## ✅ Validation

- All incoming `request.body` data is validated using a `validateBody` middleware
- Ensures strong API contract with the frontend

---

## 🗂 Project Structure

```
/controllers     # Business logic
/middlewares     # Auth, validation, error handling
/models          # Mongoose schemas
/routes          # API routes
/utils           # Custom exceptions, helpers
/public          # Uploaded images (categories)
/temp            # Temporary storage
.env             # JWT_SECRET, DB URI, etc.
```

---

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
