# 🛒 Node.js Backend for an Online Store

📖 [Прочитать на русском](./README.ru.md)  📖 [Auf Deutsch lesen](./README.de.md)
--
A high-performance **RESTful API** built with **Node.js + Express** for real e-commerce scenarios:  
secure **JWT** authentication, role-based access (**RBAC**), product/order management,  
image uploads (**Multer**), and **real-time** events via **WebSocket** (order statuses, admin notifications).  
Data is stored in **MongoDB** with models defined via **Mongoose**.

**Impact:** Reduced order processing time and improved checkout reliability  
through REST architecture, RBAC, WebSocket status updates, secure JWT authentication,  
and MongoDB/Mongoose.

---

## 🧱 Selected Technologies & Why (Business Value → Problem Solved)

| Technology | Business Value | Problem Solved |
|------------|----------------|----------------|
| **Node.js** (non-blocking I/O) | Handles **thousands of customers in parallel** without slowing down checkout | Bottlenecks & delays during peak sales (e.g., Black Friday) |
| **TypeScript** (typed DTOs & models) | Prevents costly bugs and ensures **stable features for end-users** | Frontend-backend mismatches causing broken orders/catalog data |
| **Express.js** (routes & middleware) | Speeds up **time-to-market** with structured, reusable routes | Messy codebases that slow feature delivery & raise dev costs |
| **MongoDB** (NoSQL) | Adapts quickly to **fast-changing product catalogs** | Rigid SQL schemas make adding attributes expensive |
| **Mongoose** (ODM) | Keeps data **clean & consistent**, avoiding order errors | Silent DB corruption → wrong inventory or orders |
| **WebSocket** (real-time) | Creates **premium UX** with instant order status & alerts | Customer frustration from delayed notifications / polling |
| **JWT** (stateless auth) | Enables **secure & scalable login** across servers | High infra costs from session storage/replication |
| **bcrypt** (password hashing) | Protects users & brand reputation by making leaks **harmless** | Financial loss & trust damage from account hacks |
| **Multer** (uploads) | Supports **rich visuals** that boost conversions | Crashes & downtime from large/bad media files |
| **CORS** (cross-origin) | Ensures smooth **SPA/SSR/mobile app integration** | Browser blocking requests from separate domains |
| **dotenv** (env management) | Reduces **deployment risks** & simplifies scaling | Leaked/hard-coded secrets, costly human mistakes |
| **RBAC** (role-based access) | Prevents **financial & operational risks** | Unauthorized actions: discounts, data leaks, costly errors |
---
## 🚀 Tech Stack

- **Node.js** + **Express.js** + **TypeScript**— RESTful API
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
