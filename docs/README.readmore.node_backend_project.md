- **Express.js** *(HTTP framework, middleware & routing)*. **Provides:** structured routes/middlewares, unified validation/logging/error handling. **Solves:** code sprawl and accelerates API delivery.

- **MongoDB** *(NoSQL document DB)*. **Provides:** flexible schema for catalogs/orders, fast indexed queries & pagination. **Solves:** frequent product model changes and scaling for traffic spikes.

- **Mongoose** *(ODM, schemas & validation)*. **Provides:** declarative schemas, hooks, model‑level validation. **Solves:** inconsistent data and silent DB errors.

- **WebSocket** *(bi‑directional real‑time)*. **Provides:** instant order status, manager alerts, live dashboards. **Solves:** expensive polling and laggy UX.

- **JSON Web Token (JWT)** *(stateless auth)*.**Provides:** session‑less tokens, horizontal scale readiness. **Solves:** session storage/replication and reduces server load.

- **bcrypt** *(password hashing with salt)*. **Provides:** secure password storage. **Solves:** account compromise risk in case of leaks.

- **Multer** *(multipart/form‑data uploads)*. **Provides:** reliable product image uploads (streaming, size limits, format filters). **Solves:** crashes due to large files and metadata issues.

- **CORS** *(Cross‑Origin Resource Sharing)*.**Provides:** safe access from a separate frontend domain/subdomain. **Solves:** browser blocking and SPA/SSR integration hurdles.

- **dotenv** *(environment variable management)*. **Provides:** clean dev/stage/prod configuration; secrets out of code. **Solves:** hard‑coded keys and deployment mistakes.

- **RBAC** *(Role‑Based Access Control: `superadmin`, `admin`, `manager`, `user`)*. **Provides:** clear boundaries via middleware (`authenticate`, `isSuperadmin`). **Solves:** unauthorized actions and operational risk.

---
