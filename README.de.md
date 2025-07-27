# 🐾 Pet Shop – Backend-API

Ein Backend-Service für ein Online-Tiergeschäft, entwickelt mit **Node.js**, **Express** und **MongoDB**.  
Diese API unterstützt Authentifizierung mit Rollen, Produkt- und Bestellverwaltung, das Hochladen von Kategoriebildern und Echtzeit-Kommunikation über WebSocket.

---

## 🚀 Tech-Stack

- **Node.js** + **Express.js** — RESTful API
- **MongoDB** + **Mongoose** — Remote-Datenbank
- **WebSocket** — Echtzeit-Kommunikation
- **jsonwebtoken (JWT)** — Token-basierte Authentifizierung
- **bcrypt** — Sichere Passwort-Hashing
- **multer** — Datei-/Bild-Upload
- **cors** — Cross-Origin-Anfragen
- **dotenv** — Verwaltung von Umgebungsvariablen

---

## 🔐 Authentifizierung & Rollen

- Anmeldung und Registrierung mit JWT
- Rollenbasierte Zugriffskontrolle:
  - `superadmin`
  - `admin`
  - `manager`
  - `user`
- Middleware:
  - `authenticate` — überprüft das JWT
  - `isSuperadmin` — beschränkt den Zugriff auf Superadmins

---

## 📁 API-Endpunkte

### `POST /api/auth`
- Benutzerregistrierung und -anmeldung
- Token-Generierung

### `GET /api/users`
- Benutzerverwaltung (nur für Admins)

### `GET /api/categories`
- Kategorien erstellen, aktualisieren und löschen
- Bild-Upload in den Ordner `public/`
- Verwendet `multer` für Bild-Upload

### `GET /api/products`
- CRUD-Operationen für Produkte

### `GET /api/orders`
- Bestellverarbeitung

---

## 🛡 Fehlerbehandlung

- `notFoundHandler` — für 404-Fehler (Route nicht gefunden)
- `errorHandler` — für interne Serverfehler
- `HttpException` — benutzerdefiniertes Utility für strukturierte Fehlermeldungen

---

## ✅ Validierung

- Alle eingehenden `request.body`-Daten werden durch Middleware `validateBody` validiert
- Gewährleistet eine stabile API-Verbindung mit dem Frontend

---

## 🗂 Projektstruktur
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

