ShikshaSetu | Full-Stack AI-Powered LMS | GitHub
=================================================

Sep 2025

Live: Coming soon 🚀

Project Snapshot
- **Tech Stack**: MongoDB, Express.js, React (Vite), Node.js, Tailwind CSS, Gemini API, Redux Toolkit
- **Key Integrations**: JWT auth, Google OAuth, Razorpay payments, Cloudinary media, Gemini AI search
- **Highlights**: role-based access (3 roles), JWT authentication, Google OAuth, Razorpay payments, Cloudinary uploads, AI-powered search via Gemini API, Redux Toolkit state management.

What I found (code analysis)
- Backend: `backend/` — Express server (`index.js`) with routes for auth, users, courses, payments and reviews. Uses `@google/genai` to power AI search (see `backend/controller/searchController.js`).
- Frontend: `frontend/` — React + Vite app with Redux Toolkit slices and Tailwind integration.
- Database: MongoDB (via Mongoose). Connect string in `process.env.MONGODB_URL`.
- Media: Cloudinary used for thumbnails and lecture video uploads (`backend/config/cloudinary.js`).
- Payments: Razorpay integration in `backend/controller/orderController.js`.
- Email: Nodemailer for OTP / password reset (`backend/config/sendMail.js`).

Core Features
- ✅ Role-based access control (3 roles) — creator, student, admin (implemented via `role` on `User` model).
- ✅ JWT-based authentication and cookie usage (`backend/config/token.js`, `middleware/isAuth.js`).
- ✅ Google Sign-In flow endpoint (`/api/auth/googleauth`).
- ✅ Course + Lecture CRUD with Cloudinary uploads (`/api/course/*`).
- ✅ Razorpay order creation and verification (`/api/order/*`).
- ✅ AI smart-search using Gemini API — interprets user intent and searches by keyword/regex fallback (`/api/course/search`).
- ✅ Reviews and ratings endpoints (`/api/review/*`).

Performance & UX Notes (from code)
- The Gemini AI call returns a single keyword and the backend falls back to regex search, improving discovery.
- Multer stores uploads to a local `public` folder before Cloudinary upload — consider direct streaming for large files.
- CORS is currently locked to `http://localhost:5173`; update for production.

Environment Variables (required)
- `PORT` — server port
- `MONGODB_URL` — MongoDB connection string
- `JWT_SECRET` — JWT signing secret
- `CLOUDINARY_NAME`, `CLOUDINARY_API_KEY`, `CLOUDINARY_API_SECRET` — Cloudinary creds
- `RAZORPAY_KEY_ID`, `RAZORPAY_KEY_SECRET` — Razorpay keys
- `GEMINI_API_KEY` — Gemini / Gemini-compatible API key
- `USER_EMAIL`, `USER_PASSWORD` — SMTP credentials used by Nodemailer

Quick Start

Backend (development)
```bash
cd backend
npm install
# create a .env with the variables above
npm run dev
```

Frontend (development)
```bash
cd frontend
npm install
npm run dev
```

API Quick Links
- Auth: `/api/auth/*` — signup, login, logout, OTP, reset, google auth
- User: `/api/user/*` — profile, current user
- Course: `/api/course/*` — create, edit, publish, lectures, search
- Order: `/api/order/*` — razorpay-order, verifypayment
- Review: `/api/review/*` — create/get reviews

System Flow (Mermaid)
```mermaid
flowchart LR
  U[User / Browser] -->|HTTP(S)| F[React Frontend (Vite)]
  F -->|API requests| B[Express Backend]
  B -->|reads/writes| DB[(MongoDB)]
  B -->|upload| C[Cloudinary]
  B -->|payment| R[Razorpay]
  B -->|AI search| G[Gemini API (@google/genai)]
  B -->|email| E[Nodemailer / Gmail SMTP]
  F -->|static assets| CDN[Cloudinary/Static Host]
  style B fill:#f9f,stroke:#333,stroke-width:1px
```

Design Considerations & Suggestions
- Move large file uploads to stream directly to Cloudinary (avoid local disk I/O) to improve performance and reliability.
- Add rate-limiting and input sanitation around AI calls to control quota and cost.
- Add server-side validation and stricter CORS for production.
- Consider storing hashed metadata for analytics (search clicks, enrollments) to verify the claimed metrics.

Repository Structure (quick)
- `backend/` — Express server, controllers, routes, models, config
- `frontend/` — React app, components, pages, Redux slices

Metrics (as requested)
- "Improved content discovery by 40%+ and reduced page load time by 30%" — architectural changes noted that enable these gains: AI-assisted category extraction, selective regex fallback, and client-side state via Redux Toolkit. (Benchmarks should be added measuring before/after to validate.)

Credits
- Built with ❤️ and AI — Gemini API

Want me to: run the server, add a CI workflow, or draft CONTRIBUTING.md next? 👇
- Open an issue or tell me which task to do next.

