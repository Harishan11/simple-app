# Simple App

Frontend: React.js
Backend: Node.js + Express.js
Database: MongoDB

employee directory with JWT login and role-based redirect.

## Run
1. Start MongoDB locally (or use an Atlas URI).
2. Backend:
   cd server && cp .env.example .env   # edit JWT_SECRET / MONGO_URI
   npm install && npm run seed && npm run dev
   (On first start the API fetches employees from dummyjson.com into MongoDB.)
3. Frontend:
   cd client && npm install && npm run dev   # http://localhost:5173

## Demo logins
- admin@example.com / admin123  -> /admin (can refresh data from the source API)
- user@example.com / user123    -> /dashboard (read-only list)

## API
POST /api/auth/login
GET  /api/employees?page&limit&search&department&sort&order   (auth)
GET  /api/employees/departments                                (auth)
POST /api/employees/sync                                       (admin only)
