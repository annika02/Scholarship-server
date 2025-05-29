# Scholarship Hub Backend

This is the backend server for the **Scholarship Hub** application, built with Node.js and Express. It provides APIs for managing users, scholarships, reviews, applications, and payment processing. The server connects to a MongoDB database hosted on MongoDB Atlas and integrates with Stripe for payment intents. It is currently deployed on Vercel at [https://scholarship-server-beta.vercel.app/](https://scholarship-server-beta.vercel.app/).

## Features

- User authentication and role management (admin, moderator, user).
- CRUD operations for scholarships, reviews, and applications.
- API endpoints for fetching and updating data in real-time.
- Integration with Stripe for payment processing.
- Admin and moderator authorization middleware for restricted access.
- CORS support for cross-origin requests.

## Technologies Used

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB (via MongoDB Atlas)
- **Payment Gateway**: Stripe
- **Middleware**: CORS, Express JSON parser
- **Hosting**: Vercel
- **Environment**: dotenv for environment variables

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- MongoDB Atlas account
- Stripe account (for payment integration)
- Vercel account (for deployment)

## Installation

1. **Clone the Repository**:
   ```bash
   git clone <your-repo-url>
   cd scholarship-hub-backend
   ```
