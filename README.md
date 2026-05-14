<div align="center">

# TechMallPK — Backend API

**Express.js · MongoDB · JWT · Cloudinary · Vercel Serverless**

[![Live API](https://img.shields.io/badge/Live%20API-toys--ecommerce--backend.vercel.app-black?style=flat-square&logo=vercel)](https://toys-ecommerce-backend.vercel.app)
[![JavaScript](https://img.shields.io/badge/JavaScript-100%25-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Node.js](https://img.shields.io/badge/Runtime-Node.js%2018-339933?style=flat-square&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Framework-Express%205-000000?style=flat-square&logo=express)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Deployed on Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-black?style=flat-square&logo=vercel)](https://vercel.com/)

</div>

---

## Overview

**TechMallPK Backend** is a production-grade REST API powering a full e-commerce platform built for the Pakistani market. Built with Express.js 5, MongoDB/Mongoose, and JWT authentication — it handles user auth (including Google OAuth2), product management with Cloudinary media uploads, shopping cart, wishlists, order management, and mobile payment processing (JazzCash & Easypaisa).

Deployable on both **Vercel** (serverless) and **AWS Lambda**.

🔗 **Live API:** [toys-ecommerce-backend.vercel.app](https://toys-ecommerce-backend.vercel.app)  
📦 **Repo:** [github.com/Hamid-GenAI-Eng/TechMallPK-backend](https://github.com/Hamid-GenAI-Eng/TechMallPK-backend)

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Runtime** | Node.js 18 |
| **Framework** | Express.js 5.2 |
| **Database** | MongoDB (Mongoose 9) |
| **Authentication** | JWT (jsonwebtoken 9) + Google OAuth2 |
| **Password Hashing** | bcryptjs |
| **Media Storage** | Cloudinary + Multer |
| **Validation** | Joi |
| **Email** | Nodemailer (Gmail SMTP) |
| **Security** | Helmet · express-rate-limit · CORS |
| **Deployment** | Vercel Serverless · AWS Lambda (optional) |

---

## Project Structure
```
TechMallPK-backend/
├── src/
│   ├── server.js                       # Express app entry point
│   ├── modules/
│   │   ├── auth/
│   │   │   ├── auth.routes.js          # Auth endpoints
│   │   │   ├── auth.controller.js      # Register, login, Google OAuth
│   │   │   ├── auth.validation.js      # Joi schemas
│   │   │   └── user.model.js           # Mongoose user model
│   │   ├── products/
│   │   │   ├── product.routes.js       # Admin product management
│   │   │   ├── product.public.routes.js # Public catalog
│   │   │   ├── product.controller.js   # CRUD + filtering + CSV export
│   │   │   ├── product.model.js        # Product schema
│   │   │   └── product.validation.js   # Joi validation
│   │   ├── orders/
│   │   │   ├── order.routes.js         # Order endpoints
│   │   │   ├── order.controller.js     # Checkout, tracking, admin stats
│   │   │   ├── order.model.js          # Order schema
│   │   │   └── payment.service.js      # JazzCash / Easypaisa
│   │   ├── cart/
│   │   │   ├── cart.routes.js
│   │   │   ├── cart.controller.js
│   │   │   └── cart.model.js
│   │   └── wishlist/
│   │       ├── wishlist.routes.js
│   │       ├── wishlist.controller.js
│   │       └── wishlist.model.js
│   ├── middleware/
│   │   ├── authMiddleware.js           # JWT verification + admin RBAC
│   │   └── uploadMiddleware.js         # Cloudinary multer adapter
│   ├── config/
│   │   └── cloudinary.js              # Cloudinary config
│   └── utils/
│       ├── emailService.js            # Nodemailer email sender
│       ├── seeder.js                  # Admin user seeder
│       └── validators.js              # Shared validators
├── vercel.json                         # Vercel deployment config
├── serverless.yml                      # AWS Lambda config
└── package.json

```

---

## API Reference

### Authentication — `/api/auth`

| Method | Endpoint | Description | Auth |
|---|---|---|---|
| POST | `/api/auth/register` | Register with email verification | Public |
| POST | `/api/auth/login` | Email / password login | Public |
| POST | `/api/auth/verify-email` | Verify email token | Public |
| POST | `/api/auth/google` | Google OAuth2 login / signup | Public |

### Products — `/api/products` & `/api/admin/products`

| Method | Endpoint | Description | Auth |
|---|---|---|---|
| GET | `/api/products` | Public catalog (paginated, filtered) | Public |
| GET | `/api/products/:id` | Product details | Public |
| GET | `/api/products/search` | Search products | Public |
| GET | `/api/admin/products` | Admin product list + stats | Admin |
| POST | `/api/admin/products` | Create product (with media upload) | Admin |
| PUT | `/api/admin/products/:id` | Update product | Admin |
| DELETE | `/api/admin/products/:id` | Delete product | Admin |

### Cart — `/api/cart`

| Method | Endpoint | Description | Auth |
|---|---|---|---|
| GET | `/api/cart` | Get user cart | Protected |
| POST | `/api/cart` | Add item to cart | Protected |
| DELETE | `/api/cart/:productId` | Remove from cart | Protected |

### Wishlist — `/api/wishlist`

| Method | Endpoint | Description | Auth |
|---|---|---|---|
| GET | `/api/wishlist` | Get wishlist | Protected |
| POST | `/api/wishlist` | Add to wishlist | Protected |
| DELETE | `/api/wishlist/:productId` | Remove from wishlist | Protected |
| GET | `/api/wishlist/check/:productId` | Check if wishlisted | Protected |

### Orders — `/api/orders`

| Method | Endpoint | Description | Auth |
|---|---|---|---|
| POST | `/api/orders` | Checkout / create order | Protected |
| GET | `/api/orders/myorders` | User's order history | Protected |
| GET | `/api/orders/:id` | Order details | Protected |
| GET | `/api/orders/admin` | All orders (paginated) | Admin |
| GET | `/api/orders/admin/stats` | Revenue & order stats | Admin |
| PUT | `/api/orders/:id` | Update status + courier info | Admin |

---

## Getting Started

### Prerequisites

- Node.js 18+
- MongoDB Atlas account
- Cloudinary account
- Gmail account (for Nodemailer)
- Google Cloud project (for OAuth2)

### Installation

```bash
git clone https://github.com/Hamid-GenAI-Eng/TechMallPK-backend.git
cd TechMallPK-backend
npm install
```

### Environment Setup

Create a `.env` file in the root:

```env
MONGO_URI=your-mongodb-connection-string
JWT_SECRET=your-jwt-secret

CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret

GOOGLE_CLIENT_ID=your-google-client-id

EMAIL_USER=your-gmail-address
EMAIL_PASS=your-gmail-app-password
FROM_NAME=TechMallPK
CLIENT_URL=http://localhost:5173

PORT=5000
NODE_ENV=development
```

### Run Locally

```bash
npm run dev
```

Server starts at `http://localhost:5000`

### Seed Admin User

```bash
node src/utils/seeder.js
```

---

## Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start with nodemon (auto-reload) |
| `npm start` | Start production server |
| `npm run sls:offline` | Run locally with Serverless offline |
| `npm run deploy` | Deploy to AWS Lambda |

---

## Security

| Feature | Implementation |
|---|---|
| Password Hashing | bcryptjs (10 salt rounds) |
| JWT Auth | 30-day expiry · HS256 |
| Email Verification | 24-hour token expiry |
| Rate Limiting | 100 req / 15 min on auth routes |
| HTTP Headers | Helmet.js |
| CORS | Whitelisted origins only |
| Admin Access | Role-based middleware |
| File Uploads | Cloudinary (10MB limit · jpg/png/webp/mp4) |
| Input Validation | Joi schemas on all endpoints |

---

## Response Format

```json
// Success
{ "success": true, "message": "Operation successful", "data": { } }

// Error
{ "message": "Error description", "details": { } }

// Paginated
{
  "pagination": { "current_page": 1, "per_page": 10, "total_pages": 5, "total_items": 50 },
  "data": [ ]
}
```

---

## Deployment

### Vercel (Primary)

```bash
vercel --prod
```

### AWS Lambda (Optional)

```bash
npm run deploy
```

---

## Built By

**[Code Envision Technologies](https://codeenvisiontechnologies.com)**

Developed by **Hamid Saifullah** — Tech Lead at [Code Envision Technologies](https://codeenvisiontechnologies.com)

[![GitHub](https://img.shields.io/badge/GitHub-Hamid--GenAI--Eng-181717?style=flat-square&logo=github)](https://github.com/Hamid-GenAI-Eng)
[![Portfolio](https://img.shields.io/badge/Portfolio-hamid--saifullah-black?style=flat-square&logo=vercel)](https://hamid-saifullah-portfolio-nexus.vercel.app)
[![Code Envision Technologies](https://img.shields.io/badge/Company-Code%20Envision%20Technologies-0A66C2?style=flat-square)](https://codeenvisiontechnologies.com)
