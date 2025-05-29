# 🎓 Scholarship Hub Backend

This is the backend server for the **Scholarship Hub** application, built with **Node.js** and **Express**. It provides RESTful APIs to manage users, scholarships, applications, reviews, and payments. It connects to a **MongoDB Atlas** database and integrates **Stripe** for secure payment processing.

🚀 Live URL: [https://scholarship-server-beta.vercel.app](https://scholarship-server-beta.vercel.app)

---

## ✨ Features

- 🔐 User Authentication & Role Management (admin, moderator, user)
- 🎓 Scholarship CRUD (Create, Read, Update, Delete)
- ✍️ Review system for scholarships
- 📄 Application submission and tracking
- 💳 Stripe payment integration
- 🔒 Role-based access control with middleware
- 🌐 CORS-enabled for frontend compatibility

---

## 🛠️ Technologies Used

| Category        | Tools                       |
| --------------- | --------------------------- |
| Runtime         | Node.js                     |
| Framework       | Express.js                  |
| Database        | MongoDB (via MongoDB Atlas) |
| Payment Gateway | Stripe                      |
| Middleware      | CORS, Express JSON parser   |
| Environment     | dotenv                      |
| Deployment      | Vercel                      |

---

## 📦 Prerequisites

- Node.js v14 or higher
- MongoDB Atlas account
- Stripe account
- Vercel account (optional, for deployment)

---

## ⚙️ Installation

1. **Clone the Repository**

   ```bash
   git clone <your-repo-url>
   cd scholarship-hub-backend
   ```

2. **Install Dependencies**

   ```bash
   npm install
   # or
   yarn install
   ```

3. **Create Environment Variables**
   Create a `.env` file in the root directory:

   ```env
   MONGODB_URI=your_mongodb_connection_string
   STRIPE_SECRET_KEY=your_stripe_secret_key
   PORT=5000
   ```

4. **Run the Server**

   ```bash
   # For development
   npm run dev

   # For production
   npm start
   ```

---

## 🔗 API Reference

<details>
<summary><strong>👤 User Management</strong></summary>

| Method | Endpoint           | Description       | Required Role | Payload / Query                |
| ------ | ------------------ | ----------------- | ------------- | ------------------------------ |
| POST   | `/create-user`     | Create a new user | None          | `{ displayName, email }`       |
| GET    | `/users/:email`    | Get user by email | None          | None                           |
| GET    | `/all-users`       | Get all users     | Admin         | email (query param)            |
| DELETE | `/delete-user/:id` | Delete a user     | Admin         | email (query param)            |
| PATCH  | `/update-role/:id` | Update user role  | Admin         | role (query param, e.g. admin) |

</details>

<details>
<summary><strong>🎓 Scholarship Management</strong></summary>

| Method | Endpoint                  | Description                     | Role            |
| ------ | ------------------------- | ------------------------------- | --------------- |
| GET    | `/`                       | Get home page scholarships      | None            |
| GET    | `/all-data`               | Get all scholarships            | None            |
| GET    | `/scholarship/:id`        | Get scholarship by ID + reviews | None            |
| POST   | `/add-scholarship`        | Add a new scholarship           | Admin/Moderator |
| DELETE | `/delete-scholarship/:id` | Delete a scholarship            | Admin/Moderator |
| PATCH  | `/update-scholarship/:id` | Update a scholarship            | Admin/Moderator |
| GET    | `/all-collections-data`   | Get all collections             | None            |

</details>

<details>
<summary><strong>📝 Review Management</strong></summary>

| Method | Endpoint             | Description                   | Role            |
| ------ | -------------------- | ----------------------------- | --------------- |
| POST   | `/add-review/:id`    | Add a review                  | None            |
| GET    | `/get-reviews/:id`   | Get reviews by scholarship ID | None            |
| GET    | `/my-review/:id`     | Get reviews by user ID        | None            |
| GET    | `/all-reviews`       | Get all reviews               | Admin/Moderator |
| DELETE | `/delete-review/:id` | Delete a review               | None            |
| PATCH  | `/update-review/:id` | Update a review               | None            |

</details>

<details>
<summary><strong>📄 Application Management</strong></summary>

| Method | Endpoint                  | Description           | Role            |
| ------ | ------------------------- | --------------------- | --------------- |
| GET    | `/all-application`        | Get all applications  | Admin/Moderator |
| GET    | `/my-application`         | Get user applications | None            |
| POST   | `/add-application`        | Add a new application | None            |
| DELETE | `/delete-application/:id` | Delete an application | None            |
| PATCH  | `/update-application/:id` | Update an application | None            |
| PATCH  | `/update-feedback/:id`    | Update feedback       | Admin/Moderator |

</details>

<details>
<summary><strong>💳 Payment Gateway</strong></summary>

| Method | Endpoint                 | Description                    | Role |
| ------ | ------------------------ | ------------------------------ | ---- |
| POST   | `/create-payment-intent` | Create a Stripe payment intent | None |

</details>

---

## 🗂️ Database Collections

| Collection       | Description                                                           |
| ---------------- | --------------------------------------------------------------------- |
| **Users**        | Stores user data: `{ userName, userEmail, role }`                     |
| **Scholarships** | Scholarship data: `{ scholarshipName, universityName, degree, fees }` |
| **Reviews**      | Review data: `{ postId, userId, comment, ratings }`                   |
| **Applications** | Application data: `{ userId, scholarshipId, status }`                 |

---

## 🤝 Contributing

1. Fork the repository
2. Create a new branch: `git checkout -b feature-name`
3. Make changes and commit: `git commit -m "Added feature"`
4. Push to your fork: `git push origin feature-name`
5. Submit a Pull Request

---
