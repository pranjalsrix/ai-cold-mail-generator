# ⚙️ AI Cold Email Generator — Developer Guide

This document contains **complete setup, configuration, testing, and deployment instructions**.

---

# 🚀 1. Prerequisites

### Required Accounts

* MongoDB Atlas → https://www.mongodb.com/cloud/atlas
* Groq API → https://console.groq.com/keys
* Gmail (for OTP emails)

---

# 🔑 2. Environment Setup

## Backend (`/server/.env`)

```env
PORT=5000
MONGODB_URI=your_mongodb_connection
JWT_SECRET=your_secure_secret
GROQ_API_KEY=your_api_key
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password
FRONTEND_URL=http://localhost:5173
```

## Frontend (`/client/.env`)

```env
VITE_API_URL=http://localhost:5000/api
```

---

# 📦 3. Installation

```bash
npm run install:all
```

OR manually:

```bash
cd server && npm install
cd ../client && npm install
```

---

# ▶️ 4. Run Development Server

```bash
npm run dev
```

---

# 🧪 5. API Testing (Postman)

### Register

```
POST /api/auth/register
```

### Verify OTP

```
POST /api/auth/verify-otp
```

### Login

```
POST /api/auth/login
```

### Generate Email

```
POST /api/ai/generate-email
Authorization: Bearer <token>
```

### Get History

```
GET /api/ai/history
```

---

# 🐳 6. Docker Setup

```bash
docker-compose up --build
```

### Services:

* Frontend container
* Backend container

---

# 🚀 7. Deployment

## Backend (Render)

* Root Directory: `server`
* Build Command: `npm install`
* Start Command: `node server.js`

Add environment variables from `.env`.

---

## Frontend (Vercel)

* Root Directory: `client`
* Framework: Vite

Add:

```
VITE_API_URL=<backend_url>/api
```

---

## Database

* Use MongoDB Atlas (recommended)

---

# 🐛 8. Troubleshooting

### MongoDB Connection Error

* Check URI
* Go to MongoDB Atlas → Network Access [Add IP: 0.0.0.0/0]

### API Errors

* Verify API keys
* Check environment variables

### Email Not Sending

* Use Gmail App Password
* Enable 2FA

---

