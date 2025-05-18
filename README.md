# Full-Stack E-Commerce Platform


A scalable, full-stack e-commerce platform built with Node.js, Express, MongoDB, and a responsive frontend. The application supports product management, inventory tracking, order processing, user authentication, and admin functionalities—providing a seamless shopping experience for users and robust management tools for administrators.

---

## 📚 Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)

---

## 🗂 Project Structure
```bash
e-commerce-website/
├── src/
│   ├── controllers/        # API logic (product, auth, inventory, etc.)
│   ├── middleware/         # Authentication middleware
│   ├── models/             # Mongoose schemas (Product, User, Order, etc.)
│   ├── public/             # Frontend assets (HTML, CSS, JS, images)
│   ├── routes/             # API route definitions
│   └── scripts/            # Database seeding scripts
├── package.json            # Dependencies and scripts
├── requirements.txt        # Python dependencies (if applicable)
├── index.html              # Admin dashboard HTML
├── style.css               # Admin dashboard styles
├── dashboard.js            # Admin dashboard JavaScript
└── README.md               # Project documentation
```
## 🚀 Features

### User Features
- Browse products by category (Men's, Women's, Children's) with search, filtering, and pagination.
- Add products to cart, manage cart items, and proceed to checkout.
- User authentication with JWT (signup, login, Google Sign-In, password updates).
- View order history, track orders, and manage profile details.
- Responsive UI with pages for FAQs, returns, customer service, and more.

### Admin Features
- Admin dashboard for managing products, inventory, orders, and discounts.
- Approve product backlogs and mark orders as shipped.
- Role-based access control (admin, superadmin) with secure authentication.
- Inventory management with automated stock updates and restocking capabilities.

### Additional Features
- Database seeding scripts for products, orders, discounts, and reviews.
- Secure API with Helmet, CORS, and content security policies.
- Integration with Bootstrap, Font Awesome, and custom CSS for enhanced UI/UX.

---

## 🧰 Technologies

### Backend
- Node.js, Express.js
- MongoDB with Mongoose
- JWT (jsonwebtoken) for authentication
- bcryptjs for password hashing
- Helmet, CORS, Morgan for security and logging
- Google Auth Library for Google Sign-In

### Frontend
- HTML, CSS, JavaScript
- Bootstrap, Font Awesome
- Custom scripts for dynamic interactions (e.g., cart, product filtering)

### Development Tools
- Nodemon
- dotenv for environment variables
- MongoDB Atlas or local MongoDB

### Deployment
- Configurable for Heroku, Vercel, Render, etc.

---

## ⚙️ Installation

Follow these steps to set up the project locally:

### Clone the repository:
```bash
git clone https://github.com/mohamedmostafam0/e-commerce-website.git
cd e-commerce-website
```
### Install dependencies
```bash
npm install
```

### Create a `.env` file
In the root directory of the project, create a `.env` file and add the following environment variables:
```bash
MONGODB_URI=mongodb://localhost:27017/jwt-auth
JWT_SECRET=your_jwt_secret_key
GOOGLE_CLIENT_ID=your_google_client_id
NODE_ENV=development
```

To populate the database with sample data, run the following seeding scripts:

```bash
node src/scripts/seedProducts.js
node src/scripts/seedAdmins.js
node src/scripts/seedOrders.js
node src/scripts/seedDiscount.js
node src/scripts/seedReviews.js
```

##🚀 Start the Server
To start the development server:
```bash
npm run dev
```
The server will be available at http://localhost:8000

## 📡 API Endpoints

Here are some key API endpoints categorized by functionality:

---

### 🛍️ Products

- `GET /api/products`  
  Fetch all products with support for filtering, sorting, and pagination.

- `GET /api/products/:id`  
  Fetch a single product by its ID.

- `POST /api/products`  
  Create a new product. *(Admin only)*

---

### 🔐 Authentication

- `POST /signup`  
  Register a new user.

- `POST /signin`  
  Log in a user via email/password or Google Sign-In.

- `GET /logout`  
  Clear JWT cookie and log the user out.

---

### 🛠️ Admin

- `POST /api/admin/login`  
  Log in as an admin.

- `GET /api/admin/profile`  
  Retrieve the authenticated admin's profile.

---

### 📦 Orders

- `GET /api/orders`  
  Fetch all orders. *(Admin only)*

- `POST /api/orders`  
  Create a new order.

---

### 🧮 Inventory

- `GET /api/inventory`  
  Retrieve inventory items. *(Admin only)*

- `POST /api/inventory/:sku/restock`  
  Restock a specific item by SKU. *(Admin only)*

---

### 🎟️ Discounts

- `GET /api/discount`  
  Fetch all available discounts.

- `POST /api/discount`  
  Create a new discount. *(Admin only)*

---

> 📁 For a complete list of endpoints and implementation details, refer to the route files in the `src/routes` directory.

