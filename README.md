# takeEat - Server

## Overview

The server-side of **takeEat** provides a robust backend for handling authentication, menu management, shopping cart functionality, payments, and administrative controls using **Express.js** and **MongoDB**. It also integrates with **Stripe** for payment processing and includes role-based access control for secure operations.

## WakaTime Reports

[![wakatime](https://wakatime.com/badge/user/5225e8ed-9a14-4fe9-b3f5-b0a5b485c255/project/bd8cb4b7-fcf4-43cb-b101-fec87cd048ad.svg)](https://wakatime.com/badge/user/5225e8ed-9a14-4fe9-b3f5-b0a5b485c255/project/bd8cb4b7-fcf4-43cb-b101-fec87cd048ad)

## Important Links

- [Live Link](https://take-eat-marjan.netlify.app/)
- [Client Repo](https://github.com/marjanhasan/takeEat-client)

## Key Features

- **Authentication & Authorization**: Role-based control with JWT and Firebase integration.
- **Cart & Payments**: Shopping cart management and Stripe payment processing.
- **Admin Controls**: User role management, CRUD operations for menu items, and platform statistics.
- **Data Aggregation**: Analytics for revenue, order stats, and user counts.

## Tech Stack

- **Backend Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: Firebase, JWT
- **Payments**: Stripe

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/takeEat-server.git
   cd takeEat-server
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up environment variables:

   - Create a `.env` file in the root directory.
   - Add the following keys:

   ```env
   DB_USER=your_userID
   DB_PASS=your_db_password
   ACCESS_TOKEN_SECRET=your_access_token_secret
   STRIPE_SECRET_KEY=your_stripe_secret_key
   ```

4. Start the server:
   ```bash
   npm start
   ```

## API Endpoints

### Menu Management

| Method | Endpoint    | Description              | Authorization |
| ------ | ----------- | ------------------------ | ------------- |
| GET    | `/menu`     | Fetch all menu items     | None          |
| GET    | `/menu/:id` | Fetch a menu item by ID  | None          |
| POST   | `/menu`     | Add a new menu item      | Admin         |
| PATCH  | `/menu/:id` | Update a menu item by ID | Admin         |
| DELETE | `/menu/:id` | Delete a menu item by ID | Admin         |

### Review Management

| Method | Endpoint   | Description                | Authorization |
| ------ | ---------- | -------------------------- | ------------- |
| GET    | `/reviews` | Fetch all customer reviews | None          |

### User Management

| Method | Endpoint              | Description                 | Authorization |
| ------ | --------------------- | --------------------------- | ------------- |
| GET    | `/users`              | Fetch all users             | Admin         |
| GET    | `/users/admin/:email` | Check if a user is an admin | Token         |
| POST   | `/users`              | Register a new user         | None          |
| DELETE | `/users/:id`          | Delete a user by ID         | Admin         |
| PATCH  | `/users/:id`          | Promote a user to admin     | Admin         |

### Cart Management

| Method | Endpoint     | Description                        | Authorization |
| ------ | ------------ | ---------------------------------- | ------------- |
| GET    | `/carts`     | Fetch cart items for a user        | Token         |
| POST   | `/carts`     | Add an item to the cart            | Token         |
| DELETE | `/carts/:id` | Remove an item from the cart by ID | Token         |

### Payment Integration

| Method | Endpoint                 | Description                                    | Authorization |
| ------ | ------------------------ | ---------------------------------------------- | ------------- |
| POST   | `/create-payment-intent` | Create a payment intent using Stripe           | Token         |
| GET    | `/payments/:email`       | Fetch payment history for a user               | Token         |
| POST   | `/payments`              | Process a payment and clear related cart items | Token         |

### Admin Statistics

| Method | Endpoint       | Description                                              | Authorization |
| ------ | -------------- | -------------------------------------------------------- | ------------- |
| GET    | `/admin-stats` | Get statistics on users, menu items, orders, and revenue | Admin         |

### Order Statistics

| Method | Endpoint       | Description                                  | Authorization |
| ------ | -------------- | -------------------------------------------- | ------------- |
| GET    | `/order-stats` | Get category-wise order quantity and revenue | Admin         |

### General

| Method | Endpoint | Description                    | Authorization |
| ------ | -------- | ------------------------------ | ------------- |
| GET    | `/`      | Check if the server is running | None          |

## Authentication and Authorization

- **verifyToken** middleware protects endpoints that require logged-in users.
- **verifyAdmin** ensures only users with admin privileges can access admin routes.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

---
