# 🛒 Ecom Farm - Role-Based E-Commerce Platform

Ecom Farm is a scalable, full-stack **Role-Based E-Commerce System** built using the modern **FARM Stack**. It supports dedicated workflows for both **Buyers** and **Sellers**, featuring secure authentication, a sleek UI, and a production-ready cloud architecture.

---

## 🚀 Features

- **🔑 Role-Based Authentication:** Dedicated dashboards for Buyers and Sellers using secure JWT-based auth.
- **🏪 Seller Module:** Complete product management, multi-image uploads (via Cloudinary), and inventory tracking.
- **🛍️ Buyer Module:** Seamless product browsing, cart management, and wishlist functionality.
- **💳 Secure Checkout:** Integrated online payments via Razorpay.
- **⚡ Modern Frontend:** Fully responsive and highly interactive UI built with React.js, Tailwind CSS, and Vite.
- **🛡️ Robust Backend:** High-performance RESTful API built on FastAPI and fully validated with Pydantic.

---

## 🏗️ Tech Stack (FARM)

| Layer              | Technology                           |
| ------------------ | ------------------------------------ |
| **Frontend**       | React.js, Vite, Tailwind CSS         |
| **Backend**        | FastAPI, Python 3                    |
| **Authentication** | JWT (JSON Web Tokens)                |
| **Database**       | MongoDB (Motor Async Driver)         |
| **Media Storage**  | Cloudinary                           |
| **Payments**       | Razorpay                             |

---

## 📁 Project Structure

```text
EcomFarm/
 ├── frontend/               # React + Vite application
 │   ├── src/
 │   │   ├── components/     # Reusable UI components
 │   │   ├── pages/          # Page layouts & logic
 │   │   └── utils/          # Helpers (e.g. axiosClient)
 └── backend/                # FastAPI backend service
     ├── config/             # DB & Environment configs
     ├── controllers/        # Request handlers & logic
     ├── middlewares/        # Custom middlewares
     ├── models/             # Pydantic schemas
     ├── routes/             # API routing endpoints
     └── services/           # Core business logic
```

---

## ⚙️ Environment Variables 

Before running the application locally or deploying, create a `.env` file in both the frontend and backend directories.

### Frontend (`frontend/.env`)
*Note: Because we use Vite, these variables must start with `VITE_`.*
```env
VITE_APP_RAZORPAY_KEY_ID=your_razorpay_key_id
VITE_APP_BACKEND_URI=http://localhost:8000/api/v1  # Update for production (e.g., https://your-backend.com/api/v1)
```

### Backend (`backend/.env`)
```env
# Database
MONGO_URI=your_mongodb_connection_string
MONGO_DB=ecommerce_farm

# Authentication
JWT_AUTH_SCREATE=your_secure_jwt_secret

# Cloudinary (for Image Uploads)
API_KEY_CLOUDINARY=your_cloudinary_api_key
API_SCREATE_CLOUDINARY=your_cloudinary_api_secret
CLOUD_NAME_CLOUDINARY=your_cloudinary_cloud_name

# Razorpay
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SCREATE=your_razorpay_secret

# CORS
FRONTEND_URI=http://localhost:5173  # Update this in production to match your frontend URL
```

---

## 📦 Local Installation & Setup

### 1️⃣ Database & Media Setup
1. Create a free cluster on [MongoDB Atlas](https://www.mongodb.com/atlas) and get your connection string.
2. Create an account on [Cloudinary](https://cloudinary.com/) and grab your API Keys. Make sure the API key role has `Create`/`Upload` permissions!

### 2️⃣ Frontend Setup
```bash
cd frontend
npm install
npm run dev
```
*Your frontend will run on `http://localhost:5173`.*

### 3️⃣ Backend Setup
Ensure you have Python 3.10+ installed.
```bash
cd backend
pip install -r requirements.txt
uvicorn app:app --reload
```
*Your backend will run on `http://localhost:8000`.*

---

## ☁️ Deployment Guidelines

- **Frontend (Vercel):** When deploying the frontend, ensure you add your Environment Variables as **Config / Plaintext** (do NOT use Vercel's "Secret" toggle since `VITE_` variables must be accessible to the browser builder).
- **Backend (Render):** When deploying on Render, ensure you whitelist Render's dynamic IP address in your MongoDB Atlas Network Access rules (whitelist `0.0.0.0/0`).
- **Cloudinary:** Ensure your deployed backend Environment Variables exactly match the spelling of the keys expected in `backend/config/Env.py`.

---

## 🧑‍💻 Developer

Designed & Developed by **CodeWithKrishna**

If you love this project, please consider giving it a ⭐ Star and contributing!
