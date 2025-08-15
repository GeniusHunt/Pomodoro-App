# **Pomodoro App**

A simple, minimalistic **Pomodoro Timer** built with **HTML, CSS, JavaScript** for the frontend, **Node.js (Express)** for the backend, and **SQLite** for the database.
This app follows the Pomodoro Technique — a time-management method that breaks work into focused intervals (default 25 minutes), separated by short breaks.

## **Features**

* **Start, Pause, and Reset** timer controls.
* Default **25-minute work session**.
* Automatically saves completed sessions to the database.
* Simple API to retrieve past sessions.
* Minimal and clean interface for distraction-free use.


## **Tech Stack**

### **Frontend**

* HTML
* CSS
* JavaScript (Vanilla)

### **Backend**

* Node.js
* Express.js
* SQLite (via `sqlite3` npm package)
* CORS enabled for frontend-backend communication

## **Project Structure**

```
pomodoro-app/
│
├── backend/
│   ├── server.js         # Backend server & API logic
│   └── database.db       # SQLite database file
│
├── frontend/
│   ├── index.html        # Main UI
│   ├── style.css         # Styling
│   └── script.js         # Timer functionality
│
└── package.json
```

## **Installation & Setup**

### 1. **Clone the repository**

```bash
git clone (https://github.com/GeniusHunt/Pomodoro-App.git)
cd pomodoro-app
```

### 2. **Install backend dependencies**

```bash
npm init -y
npm install express sqlite3 cors
```

### 3. **Run the backend**

```bash
node backend/server.js
```

Backend will run on:

```
http://localhost:3000
```

### 4. **Run the frontend**

* Open `frontend/index.html` directly in your browser.
* Ensure backend is running for session saving to work.

## **API Endpoints**

| Method | Endpoint       | Description                  |
| ------ | -------------- | ---------------------------- |
| POST   | `/add-session` | Save a completed Pomodoro    |
| GET    | `/sessions`    | Retrieve all stored sessions |


## **Example API Usage**

### Save a session (POST `/add-session`)

```json
{
  "type": "work",
  "duration": 25
}
```

### Get sessions (GET `/sessions`)

```json
[
  { "id": 1, "type": "work", "duration": 25, "date": "2025-08-15T11:00:00Z" }
]
```

##**How It Works**

1. The user starts the timer in the browser.
2. After 25 minutes, the timer stops and sends a request to the backend.
3. The backend stores the session in the SQLite database.
4. The stored data can be retrieved using the `/sessions` endpoint.

##**Future Improvements**

* Adjustable work/break durations.
* Break timer functionality.
* Sound notifications.
* User authentication to save sessions per user.
* Dark/Light mode toggle.

##**License**

This project is open-source. You can modify and use it for personal or commercial purposes.


