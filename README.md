# 🛒 Node.js Backend for an Online Store

📖 [Прочитать на русском](./README.ru.md)  📖 [Auf Deutsch lesen](./README.de.md)
A high‑performance **RESTful API** built with **Node.js + Express** for real e‑commerce scenarios: secure **JWT** authentication, role‑based access (**RBAC**), product/order management, image uploads (**Multer**), and **real‑time** events via **WebSocket** (order statuses, admin notifications). Data is stored in **MongoDB** with models defined via **Mongoose**.

> **Impact:** Reduced order processing time and improved checkout reliability through REST architecture, RBAC, WebSocket status updates, secure JWT authentication, and MongoDB/Mongoose. 

---

## 🧱 Selected Technologies & Why (benefit → problem solved)

- **Node.js** *(JavaScript runtime, non‑blocking I/O)*  
  **Provides:** high concurrency with low latency.  
  **Solves:** bottlenecks and delays under peak load.

- **TypeScript** *(static typing, DTOs, typed models)*  
  **Provides:** compile‑time safety, safer refactoring, typed DTOs and models, locked API/WS contracts.  
  **Solves:** runtime bugs and frontend integration mismatches; eliminates silent catalog/order inconsistencies with typed Mongoose models.

- **Express.js** *(HTTP framework, middleware & routing)*  
  **Provides:** structured routes/middlewares, unified validation/logging/error handling.  
  **Solves:** code sprawl and accelerates API delivery.

- **MongoDB** *(NoSQL document DB)*  
  **Provides:** flexible schema for catalogs/orders, fast indexed queries & pagination.  
  **Solves:** frequent product model changes and scaling for traffic spikes.

- **Mongoose** *(ODM, schemas & validation)*  
  **Provides:** declarative schemas, hooks, model‑level validation.  
  **Solves:** inconsistent data and silent DB errors.

- **WebSocket** *(bi‑directional real‑time)*  
  **Provides:** instant order status, manager alerts, live dashboards.  
  **Solves:** expensive polling and laggy UX.

- **JSON Web Token (JWT)** *(stateless auth)*  
  **Provides:** session‑less tokens, horizontal scale readiness.  
  **Solves:** session storage/replication and reduces server load.

- **bcrypt** *(password hashing with salt)*  
  **Provides:** secure password storage.  
  **Solves:** account compromise risk in case of leaks.

- **Multer** *(multipart/form‑data uploads)*  
  **Provides:** reliable product image uploads (streaming, size limits, format filters).  
  **Solves:** crashes due to large files and metadata issues.

- **CORS** *(Cross‑Origin Resource Sharing)*  
  **Provides:** safe access from a separate frontend domain/subdomain.  
  **Solves:** browser blocking and SPA/SSR integration hurdles.

- **dotenv** *(environment variable management)*  
  **Provides:** clean dev/stage/prod configuration; secrets out of code.  
  **Solves:** hard‑coded keys and deployment mistakes.

- **RBAC** *(Role‑Based Access Control: `superadmin`, `admin`, `manager`, `user`)*  
  **Provides:** clear boundaries via middleware (`authenticate`, `isSuperadmin`).  
  **Solves:** unauthorized actions and operational risk.

---

## 💼 Business Value

- **Faster path to purchase:** robust REST endpoints + instant status updates reduce friction.  
- **Secure by default:** JWT + bcrypt + RBAC → fewer incidents and manual errors.  
- **Scale‑ready:** modular architecture, horizontal scaling, flexible data model.

---

## 📦 Tech Stack (at a glance)

**Node.js, TypeScript, Express.js, MongoDB, Mongoose, WebSocket, JSON Web Token (JWT), bcrypt, Multer, CORS, dotenv, RBAC**

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
