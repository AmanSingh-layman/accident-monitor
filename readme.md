# 🚨 LogiGuardians — Smart Delivery Accident Detection & ML Integration

**LogiGuardians** is an intelligent accident detection and emergency response system built to monitor delivery drivers in real-time using a webcam and a deep learning model. The system detects accidents, captures geolocation data, and automatically sends alerts to emergency services via email.

> 🧠 This version includes deep learning-based accident prediction using ResNet18, integrated and optimized by **Aman Singh**.

---

## 🚀 Features

- 🎥 Real-time accident detection via webcam
- 📍 Geolocation tracking using browser API
- 🧠 ML-powered prediction using ResNet18 (PyTorch)
- 🛡️ JWT-based Authentication (Login/Signup)
- 👤 Editable user profile with avatar upload
- 📨 Automatic email alerts with accident details
- 🌐 RESTful API with FastAPI backend

---

## 🛠️ Tech Stack

| Frontend              | Backend (API + DB)    | ML Model                |
|-----------------------|------------------------|--------------------------|
| React + Tailwind CSS  | FastAPI (Python)       | ResNet18 (PyTorch)       |
| React Webcam          | SQLite                 | Custom classifier        |
| Geolocation API       | JWT Auth               | OpenCV for frame capture |

---

## 🔧 Setup Instructions

### 1. Clone the Repo
```bash
git clone https://github.com/AmanSingh-layman/accident-monitor.git
```

---

### 2. Backend (FastAPI + ML)

```bash
cd backend
python -m venv venv
venv\Scripts\activate           # For Windows
pip install -r requirements.txt
```

**Run the backend server:**

```bash
uvicorn main:app --reload --port 8000
```

---

### 3. Frontend (React)

```bash
cd frontend
npm install
npm run dev
```

Visit the app at:  
📍 http://localhost:5173

---

## ✅ User Flow

1. User logs in or signs up  
2. App requests webcam and location access  
3. Webcam feed is processed via ResNet18 ML model  
4. On accident detection:
   - Geolocation is fetched
   - A report is sent to the backend
   - Email alert is triggered automatically
5. Users can update their profile (name, driver ID, avatar, etc.)

---

## 📦 Folder Structure

```
.
├── frontend/         # React + Tailwind App
├── backend/          # FastAPI + ML + DB
│   ├── model/        # ResNet18 model & prediction logic
│   ├── main.py       # FastAPI app
│   └── send_email.py # Email integration
└── README.md
```

---

## 📄 API Overview

| Method | Endpoint         | Description                        |
|--------|------------------|------------------------------------|
| POST   | `/signup`        | User registration                  |
| POST   | `/login`         | User login                         |
| PATCH  | `/profile`       | Update profile info & avatar       |
| POST   | `/predict`       | ML prediction on video frame       |
| POST   | `/report-accident` | Log & notify accident             |
| POST   | `/stop-webcam`   | Stop backend webcam stream         |

---

## 🧪 ML Model (ResNet18)

A custom-trained ResNet18 model (using transfer learning) analyzes webcam video frames in real-time. The model predicts whether an accident has occurred based on visual cues and returns a confidence score. The model is optimized for fast inference and integrated into the FastAPI backend.

---

## ✉️ Email Integration

Uses Gmail SMTP to send alerts. Configuration is handled in `send_email.py`.

**Set up `.env` in `/backend` directory:**

```env
EMAIL_HOST_USER=youremail@gmail.com
EMAIL_HOST_PASSWORD=your-app-password
SECRET_KEY=your_jwt_secret
```

> Use Gmail App Password if 2FA is enabled.

---

## 🤝 Contributors

- **Nabin Agrawal** — Fullstack Developer (React + FastAPI + Auth)
- **Aman Singh** — Machine Learning Developer (ResNet18 Accident Model, Integration, Real-time Inference)

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
