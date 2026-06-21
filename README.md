# 🎓 ShikshaSetu — Full-Stack AI-Powered Learning Management System (MERN • Gemini AI • Razorpay • Cloudinary)

An AI-powered Learning Management System (LMS) built with the MERN stack to provide an end-to-end online learning experience. ShikshaSetu enables instructors to create and manage courses while offering students a seamless platform for learning, secure payments, AI-assisted course discovery, and interactive content delivery. 🚀

## ✨ Why this project

* 🎓 Complete e-learning platform supporting students, instructors, and administrators.
* 🤖 AI-powered smart course search using the Gemini API for faster content discovery.
* 🏗️ Production-ready architecture featuring secure authentication, cloud media storage, online payments, and scalable REST APIs.

## 🧰 Tech Stack

* 🎨 Frontend: React (Vite), Tailwind CSS, Redux Toolkit
* 🖥️ Backend: Node.js, Express.js
* 🗄️ Database: MongoDB (Mongoose)
* 🤖 AI: Gemini API
* ☁️ Media Storage: Cloudinary
* 💳 Payments: Razorpay
* 🔐 Authentication: JWT, Google OAuth
* 📧 Email Service: Nodemailer
* 🚀 Deployment: Render (Backend), Vercel/Netlify (Frontend)

---

# 🔑 Core Features

* 👥 **Role-Based Access Control**

  * Student
  * Instructor
  * Admin
  * Protected dashboards for each role.

* 🔐 **Authentication & Authorization**

  * JWT Authentication
  * Google OAuth Login
  * Secure Cookies
  * OTP Verification
  * Password Reset via Email

* 📚 **Course Management**

  * Create, edit, publish, and delete courses.
  * Upload course thumbnails and lecture videos.
  * Organize lectures with structured course content.

* ☁️ **Cloudinary Integration**

  * Cloud-based image and video uploads.
  * Optimized media delivery.
  * Secure file management.

* 🤖 **AI-Powered Smart Search**

  * Natural language course search using Gemini API.
  * Intent-based keyword extraction.
  * Intelligent fallback with MongoDB regex search.
  * Improved content discovery experience.

* 💳 **Secure Payments**

  * Razorpay payment gateway integration.
  * Online course enrollment.
  * Payment verification and order validation.

* ⭐ **Reviews & Ratings**

  * Students can rate purchased courses.
  * Course review management.
  * Permission-based review operations.

* 📊 **Modern State Management**

  * Redux Toolkit for centralized application state.
  * Optimized data fetching and UI synchronization.

---

# 🏗 System Architecture

```text
Student / Instructor
          │
          ▼
 React Frontend (Vite)
          │
 REST API Requests
          │
          ▼
 Express.js Backend
          │
 ├───────────────┬──────────────┬──────────────┐
 ▼               ▼              ▼              ▼
MongoDB     Gemini API     Cloudinary     Razorpay
 │               │              │              │
 ▼               ▼              ▼              ▼
Course Data   AI Search     Media Files    Payments
```

---

# 🚀 Getting Started

## 1️⃣ Clone Repository

```bash
git clone https://github.com/UJJWAL2282/ShikshaSetu.git

cd ShikshaSetu
```

## 2️⃣ Install Dependencies

### Backend

```bash
cd backend
npm install
```

### Frontend

```bash
cd frontend
npm install
```

---

## 3️⃣ Configure Environment Variables

Create a `.env` file inside the backend directory.

```env
PORT=5000

MONGODB_URL=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

GEMINI_API_KEY=your_gemini_api_key

CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

RAZORPAY_KEY_ID=your_key
RAZORPAY_KEY_SECRET=your_secret

USER_EMAIL=your_email
USER_PASSWORD=your_email_password
```

---

## 4️⃣ Run the Project

### Backend

```bash
npm run dev
```

### Frontend

```bash
npm run dev
```

Open:

```text
http://localhost:5173
```

---

# 📁 Project Structure

```text
ShikshaSetu/

├── backend/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── utils/
│   └── index.js
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── redux/
│   │   ├── services/
│   │   └── App.jsx
│   │
│   └── public/
│
├── package.json
└── README.md
```

---

# 🛡️ Security & Performance

* 🔐 JWT-based authentication
* 🔑 Google OAuth login
* 📧 Secure OTP email verification
* ☁️ Cloudinary media storage
* 📦 Redux Toolkit state management
* ⚡ Optimized REST APIs
* 📱 Fully responsive UI
* 🗂️ Modular backend architecture

---

# 📊 Platform Modules

### 👨‍🎓 Student

* Register/Login
* Browse Courses
* AI Course Search
* Purchase Courses
* Watch Lectures
* Submit Reviews

### 👨‍🏫 Instructor

* Create Courses
* Upload Lectures
* Manage Course Content
* View Published Courses

### 👨‍💼 Admin

* Manage Users
* Monitor Platform
* Moderate Course Content

---

# 🤖 AI Smart Search

The platform integrates **Google Gemini API** to improve course discovery.

Workflow:

```text
User Query
     │
     ▼
 Gemini API
     │
Intent & Keyword Extraction
     │
     ▼
MongoDB Search
     │
     ▼
Relevant Courses
```

This approach enables users to search naturally instead of relying on exact keywords.

---

# 💳 Payment Workflow

```text
Student
    │
    ▼
Select Course
    │
    ▼
Razorpay Order
    │
    ▼
Payment Verification
    │
    ▼
Course Enrollment
```

---

# 🎯 Future Improvements

* 📹 Live Video Classes
* 💬 Course Discussion Forums
* 📈 Learning Analytics Dashboard
* 🏆 Certificates on Course Completion
* 📱 Progressive Web App (PWA)
* 🔔 Push Notifications
* 🤖 Personalized AI Course Recommendations
* 🌍 Multi-language Support

---

# 🤝 Contributing

* Fork the repository
* Create a feature branch
* Commit your changes
* Submit a Pull Request

Please follow meaningful commit messages and include screenshots for UI updates.

---

# 📄 License

MIT License

---

# 🌐 Live Demo

Coming Soon 🚀

---

Built to deliver a modern AI-powered learning experience through scalable MERN architecture, secure authentication, cloud media management, intelligent course discovery, and seamless online payments. Feedback and contributions are always welcome! 🙌
