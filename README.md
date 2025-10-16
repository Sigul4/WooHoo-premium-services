# WooHoo Backend 🚀

> **Business Context**: WooHoo is a subscription-based platform that provides premium services to users. The backend powers user onboarding, subscription management, and payment processing, enabling users to access exclusive content and features through tiered subscription plans.

A robust Node.js/Express backend application that handles user authentication 🔐, payment processing 💳, and email services 📧 for a modern subscription platform.

## ✨ Features

- **🔐 User Authentication**
  - Email/password registration and login
  - Google OAuth integration
  - Email verification system
  - Password reset functionality
  - JWT-based session management

- **💳 Payment Processing**
  - Stripe integration for payments and subscriptions
  - One-time payment checkout sessions
  - Subscription management
  - Webhook handling for payment events
  - Transaction tracking

- **📧 Email Services**
  - Nodemailer integration
  - Email verification codes
  - Password reset emails
  - Payment confirmation emails

- **🗄️ Database**
  - MongoDB with Mongoose ODM
  - User data persistence
  - Payment status tracking

## 🛠️ Tech Stack

### Core Technologies
- **⚡ Runtime**: Node.js
- **🚀 Framework**: Express.js
- **🗄️ Database**: MongoDB with Mongoose ODM
- **🔐 Authentication**: JWT (jsonwebtoken)
- **💳 Payments**: Stripe API
- **📧 Email**: Nodemailer

### Security & Validation
- **🔒 Security**: bcrypt for password hashing
- **✅ Validation**: validator.js
- **🍪 Cookies**: cookie-parser
- **🌐 CORS**: Cross-origin resource sharing

### Utilities & Libraries
- **📦 Utilities**: lodash, uuid
- **📁 File Upload**: multer
- **🌍 Environment**: dotenv
- **🔄 Development**: nodemon

### External Services
- **💳 Payment Gateway**: Stripe
- **📧 Email Service**: Gmail SMTP
- **🔐 OAuth**: Google OAuth 2.0

## 📁 Project Structure

```
woohoo_backend/
├── app.js                 # Main application entry point
├── package.json           # Dependencies and scripts
├── public/
│   └── uploads/          # File upload directory
└── src/
    ├── index.js          # Server startup
    ├── server.js         # Express app configuration
    ├── config/
    │   └── db.js         # MongoDB connection
    ├── middleware/
    │   └── authMiddleware.js  # JWT authentication middleware
    ├── routes/
    │   └── index.js      # Route definitions
    └── domains/
        ├── user/         # User management
        │   ├── controllers.js
        │   ├── index.js
        │   └── model.js
        ├── payments/     # Payment processing
        │   ├── controllers.js
        │   ├── index.js
        │   └── model.js
        ├── plans/        # Subscription plans
        │   ├── controllers.js
        │   ├── index.js
        │   └── model.js
        └── nodemailer/   # Email services
            ├── controllers.js
            └── index.js
```

## 🔌 API Endpoints

### 🔐 User Authentication
- `POST /user/signup` - User registration
- `POST /user/login` - User login
- `POST /user/google-signup` - Google OAuth signup
- `POST /user/google-login` - Google OAuth login
- `POST /user/verify` - Email verification
- `POST /user/resend-verification` - Resend verification code
- `POST /user/forgot-password` - Request password reset
- `POST /user/reset-password/:token` - Reset password
- `GET /user/logout` - User logout
- `GET /user/info` - Get user information
- `GET /user/validate-token` - Validate JWT token

### 💳 Payments
- `POST /payments/checkout` - Create checkout session
- `POST /payments/subscription` - Create subscription
- `GET /payments/prices` - Get product prices
- `POST /payments/webhook` - Stripe webhook handler

### 📧 Email Services
- `POST /nodemailer/send` - Send custom emails

## ⚙️ Environment Variables

Create a `.env` file with the following variables:

```env
# Server
PORT=5001
BASE_URL=http://localhost:3000

# Database
DATABASE_URL=mongodb://localhost:27017/woohoo

# JWT
SECRET_TOKEN=your_jwt_secret

# Email (Gmail)
GMAIL_ADDRESS=your_email@gmail.com
GMAIL_PASSWORD=your_app_password

# Stripe
STRIPE_SECRET_KEY=sk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...
PRO_PRODUCT=prod_...
CUSTOMER_PRODUCT=prod_...
```

## 🚀 Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables in `.env`

4. Start the development server:
   ```bash
   npm run dev
   ```

## 💻 Development

- **Development server**: `npm run dev` (uses nodemon for auto-restart)
- **Production server**: `node src/index.js`

## 🔒 Security Features

- Password hashing with bcrypt
- JWT tokens with expiration
- Secure HTTP-only cookies
- CORS configuration
- Input validation and sanitization
- Error handling and logging

## 🗄️ Database Models

### User Model
- Personal information (name, email)
- Authentication data (password, verification status)
- Payment status tracking
- Google OAuth integration flags

### Payment Model
- Transaction tracking
- Payment status
- Subscription management

## 🔗 Webhook Handling

The application handles Stripe webhooks for:
- Payment completion
- Subscription events
- Payment failures
- Customer subscription updates

## ⚠️ Error Handling

Comprehensive error handling for:
- Authentication failures
- Validation errors
- Database connection issues
- Payment processing errors
- Email delivery failures

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request
