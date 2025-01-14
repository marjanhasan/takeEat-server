# takeEat (Server Side)

Backend server for the takeEat application, handling data processing, user management, and payment integration.

## WakaTime reports

[![wakatime](https://wakatime.com/badge/user/5225e8ed-9a14-4fe9-b3f5-b0a5b485c255/project/bd8cb4b7-fcf4-43cb-b101-fec87cd048ad.svg)](https://wakatime.com/badge/user/5225e8ed-9a14-4fe9-b3f5-b0a5b485c255/project/bd8cb4b7-fcf4-43cb-b101-fec87cd048ad)

## Important Links

- [Live Link](https://take-eat-marjan.netlify.app/)
- [Client Repo](https://github.com/marjanhasan/takeEat-client)

## Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Setup](#setup)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)

### Features
- **User Authentication**: Handles secure login, registration, and role-based authorization.
- **Menu Management**: CRUD operations for menu items.
- **Order & Payment Processing**: Manages shopping cart operations and Stripe payments.
- **Admin Controls**: Provides administrative tools for user and payment management.
- **Sales Analytics**: Tracks and reports user activity and sales.

### Technologies Used
- **Backend Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: Firebase
- **Payment Processing**: Stripe

### Setup

1. Clone the server-side repository.
   ```bash
   git clone <server-repo-url>
   ```
2. Navigate to the project directory.
   ```bash
   cd takeEat-server
   ```
3. Install dependencies.
   ```bash
   npm install
   ```
4. Create a `.env` file in the root directory and configure your environment variables.
   ```env
   DB_USER=your_userID
   DB_PASS=your_db_password
   ACCESS_TOKEN_SECRET=your_access_token_secret
   STRIPE_SECRET_KEY=your_stripe_secret_key
   ```
5. Start the server.
   ```bash
   npm run start
   ```

### API Endpoints
| Method | Endpoint           | Description                          |
|--------|-------------------|--------------------------------------|
| GET    | /api/menu         | Fetch all menu items.                |
| POST   | /api/menu         | Add a new menu item (admin only).    |
| PUT    | /api/menu/:id    | Update a menu item (admin only).     |
| DELETE | /api/menu/:id    | Delete a menu item (admin only).     |
| POST   | /api/auth/login   | Authenticate user and generate token.|
| POST   | /api/cart         | Add items to the user’s cart.       |
| POST   | /api/payment      | Process payment with Stripe.         |

### Contributing
Contributions are welcome! Fork the repository and submit a pull request.
