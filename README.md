# ♟️ IndiChess Backend (Spring Boot) — Chess.com Style Project

IndiChess is a full-stack chess platform inspired by Chess.com, built using **Spring Boot (Backend)** and **React.js (Frontend)**.  
This repository contains the **backend API**, including authentication, matchmaking, game management, and move handling.

🔗 **Frontend Repository:**  
https://github.com/Premkumar981/indichessfrontend

---

## 🚀 Tech Stack

### ✅ Backend (This Repo)
- Java + Spring Boot
- Spring Security
- JWT Authentication (**HttpOnly Cookie**)
- Spring Data JPA + Hibernate
- MySQL Database
- OAuth2 Login (Google / GitHub)
- REST APIs

### ✅ Frontend
- React.js
- React Router DOM
- Axios
- CSS (Component-based styling)

---

## ✨ Features

### 🔐 Authentication
- User Signup & Login
- JWT token generation and validation
- JWT stored securely using **HttpOnly Cookies**
- Logout support (cookie cleared properly)
- OAuth2 login using:
  - Google
  - GitHub

### ♟️ Chess Game System
- Create & manage chess matches
- Move tracking support
- Match history support (via database entities)

### 🎯 Matchmaking
- Join match queue
- Auto-match players
- Start game after match found

---

## 🔗 Frontend + Backend Flow

1. User opens React frontend
2. Logs in / signs up (or OAuth)
3. Backend issues JWT cookie
4. Protected routes allow access:
   - `/home`
   - `/game/:matchId`
5. Game moves are sent to backend APIs
6. Logout clears JWT cookie and redirects to login

---

## 📂 Backend Project Structure
```bash
IndiChessBackend/
│
├── controller/ # API Controllers (Auth, Game, Match, User)
├── service/ # Business Logic (JWT, Auth, Matchmaking, Game)
├── repository/ # Spring Data JPA Repositories
├── model/ # Entities + DTOs
├── filters/ # JWT Filter
├── config/ # Security + CORS Configuration
└── oauth/ # OAuth2 Success Handler
```


---

## 🔥 Important API Endpoints

### Auth APIs
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/signup` | Register a new user |
| POST | `/login` | Login & set JWT cookie |
| POST | `/logout` | Logout & clear JWT cookie |
| GET | `/auth/me` | Check if user is authenticated |

---

## 🛠️ Setup & Run (Backend)

### ✅ Prerequisites
- Java 17+ (or Java 21)
- Maven
- MySQL
- IntelliJ IDEA / VS Code

---

### 1️⃣ Clone Backend Repo
```bash
git clone https://github.com/Premkumar981/chess_backend
cd IndiChessBackend
```

### 2️⃣ Configure Database

Create a MySQL database:
```bash
CREATE DATABASE indichess;
```

Update application.properties:
```bash
spring.datasource.url=jdbc:mysql://localhost:3306/indichessdb
spring.datasource.username=root
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### 3️⃣ Run Backend Server
```bash
mvn spring-boot:run
```

Backend runs at:
```bash
http://localhost:8080
```

## 🖥️ Setup & Run (Frontend)
### 1️⃣ Clone Frontend Repo
```bash
git clone https://github.com/Premkumar981/indichessfrontend
cd indichessfrontend
```

### 2️⃣ Install dependencies
```bash
npm install
```

### 3️⃣ Start frontend
```bash
npm start
```

Frontend runs at:
```bash
http://localhost:3000
```

## 🔐 Security Notes

JWT is stored in an HttpOnly cookie, which prevents direct access from JavaScript.

Protected routes are controlled using backend authentication checks.

Spring Security blocks access to protected APIs when the user is not logged in.



## 👨‍💻 Author

Prem Kumar<br>
📍 Lovely Professional University<br>
💻 Full Stack Developer | Java | Spring Boot | React
