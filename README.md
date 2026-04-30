# 🤖 ByteBot – CS Study Assistant (Full Stack)

AI-powered CS chatbot with login, registration, profile, and saved conversation history.

## Tech Stack
- **Frontend:** HTML, CSS, Vanilla JavaScript
- **Backend:** Node.js + Express
- **Database:** SQLite (via better-sqlite3)
- **Auth:** JWT + bcrypt
- **AI:** Groq API (LLaMA 3.3 70B) — FREE

---

## 🚀 Setup Instructions (Run on Your Computer)

### Step 1 — Install Node.js
Download and install from: https://nodejs.org  
(Choose the LTS version)

### Step 2 — Open this folder in terminal
```
cd bytebot
```

### Step 3 — Install dependencies
```
npm install
```

### Step 4 — Add your Groq API key
Open the `.env` file and paste your Groq API key:
```
GROQ_API_KEY=your_groq_key_here
```

### Step 5 — Start the server
```
npm start
```

### Step 6 — Open in browser
Go to: http://localhost:3000

---

## 📁 Project Structure
```
bytebot/
├── server/
│   └── index.js        ← Express server + all API routes + SQLite DB
├── public/
│   └── index.html      ← Full frontend (auth + chat + profile)
├── .env                ← API keys and config
├── package.json        ← Dependencies
└── README.md
```

## 🗄️ Database Tables
- **users** — id, name, email, hashed password, created_at
- **conversations** — id, user_id, title, created_at, updated_at
- **messages** — id, conversation_id, role (user/assistant), content, created_at

## 🔐 API Endpoints
| Method | Route | Auth | Description |
|--------|-------|------|-------------|
| POST | /api/auth/register | ❌ | Register new user |
| POST | /api/auth/login | ❌ | Login and get token |
| GET | /api/auth/profile | ✅ | Get user profile + stats |
| PUT | /api/auth/profile | ✅ | Update profile name |
| GET | /api/conversations | ✅ | List all conversations |
| POST | /api/conversations | ✅ | Create new conversation |
| GET | /api/conversations/:id/messages | ✅ | Get messages in conversation |
| DELETE | /api/conversations/:id | ✅ | Delete conversation |
| POST | /api/chat | ✅ | Send message, get AI reply |
