# UTD Food Deals Application

A full-stack web application for discovering and managing food deals, tailored for the UTD student community. Users can browse current deals, view them on an interactive map, and manage their own or saved deals through a personalised profile system.

---

## 🏗️ Project Structure

```
deal/
├── backend/             # FastAPI backend for deals, users, auth, and restaurants
│   ├── app/             # Main app source
│   │   ├── models/      # SQLAlchemy models
│   │   ├── schemas/     # Pydantic schemas
│   │   ├── routes/      # API routes (deals, auth, users, restaurants)
│   │   ├── utils/       # Auth/token utilities
│   │   └── main.py      # FastAPI app entry point
│   ├── database.py      # Database connection logic
│   └── requirements.txt # Backend dependencies
│
├── frontend/            # Next.js + React frontend
│   ├── app/             # App routes (pages)
│   ├── components/      # Reusable React components (e.g. MapComp, AddDealForm)
│   ├── styles/          # Global styles and module CSS
│   └── public/          # Static assets (images, icons)
│
└── README.md            # You're reading it!
```

---

## 🚀 Features

### ✅ Frontend (React + Next.js)
- Deal discovery with filters and search
- Interactive map with markers for restaurants & user location (Leaflet.js)
- User authentication (login, signup, token-based)
- Saved deals list & ability to remove
- Deal submission form with date and image input
- Profile page for updating user settings and managing own added deals
- Edit and delete support for user-added deals

### ✅ Backend (FastAPI + SQLAlchemy + SQLite)
- JWT-based authentication and route protection
- REST API for:
  - Deals (create, fetch, filter, update, delete)
  - Saved deals (per user)
  - Restaurants (name, cuisine, coordinates)
  - Users (register, login, update)
- Auto-expiry of deals based on end date
- Role-based ownership checks for secure deal management

---

## ⚙️ Setup Instructions

### 1. Backend (FastAPI)

```bash
cd backend
python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Make sure your `.env` or `config.py` contains your `JWT_SECRET_KEY` and database path.

### 2. Frontend (Next.js)

```bash
cd frontend
npm install
npm run dev
```

By default, the frontend expects the backend API at `http://localhost:8000/api/`.

---

## 🗃️ Technologies Used

- **Frontend**: React, Next.js, Leaflet, Axios, Tailwind CSS / CSS Modules
- **Backend**: FastAPI, Pydantic, SQLAlchemy, SQLite, JWT
- **Tools**: VSCode, Postman, Git

---

## 📌 Notes

- You must enable location permissions to see nearby deals and get accurate restaurant distances.
- Map requires internet access to load tiles from OpenStreetMap.
- Tokens are stored in localStorage; you may improve this with secure cookies in production.

---

## 👨‍💻 Future Improvements

- Pagination and search filters on deal list
- Review and rating system for restaurants
- Push/email notifications for new deals
- Admin panel for managing content

---

## 📄 License

MIT License — feel free to use, modify, and contribute!
