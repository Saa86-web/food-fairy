# food-fairy
Food Fairy
The Food Fairy is a web application designed to manage food distribution in communities, connecting food donors with beneficiaries through distribution centers. This project includes user authentication and a basic API for managing food donations.

Table of Contents
Features
Technologies Used
Setup Instructions
Usage
API Endpoints
Contributing
License
Features
User registration and login
Manage food donors, beneficiaries, distribution centers, and food types
Track food delivery records
Secure authentication with JWT
Technologies Used
Backend: Node.js, Express
Database: MySQL
Authentication: JSON Web Tokens (JWT), bcrypt for password hashing
Security: Helmet for security headers, CORS for cross-origin requests
Dependencies:
express: Web framework for Node.js
mysql2: MySQL client for Node.js
bcryptjs: Password hashing library
jsonwebtoken: Library for generating JWTs
dotenv: Environment variable management
helmet: Security middleware
cors: Middleware for enabling CORS
express-rate-limit: Basic rate-limiting middleware
Setup Instructions
Prerequisites
Node.js (v14 or higher)
MySQL Server
MySQL Workbench (optional for managing your database)
Clone the Repository
bash
Copy code
git clone https://github.com/Saa86-web/food-fairy.git
cd food-fairy
Install Dependencies
bash
Copy code
npm install
Configure Environment Variables
Create a .env file in the root of the project and add the following:

plaintext
Copy code
DB_HOST=localhost
DB_USER=your_user
DB_PASS=your_password
DB_NAME=food_fairy
JWT_SECRET=your_jwt_secret
Create Database and Table
Use MySQL Workbench or another SQL client to create the database and users table:

sql
Copy code
CREATE DATABASE food_fairy;

USE food_fairy;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);
Run the Application
Start the server:

bash
Copy code
node server.js
The application will be running at http://localhost:3000.

Usage
You can register a new user or log in using the provided API endpoints. Use tools like Postman or cURL to interact with the API.

API Endpoints
Register User
URL: /api/auth/register
Method: POST
Request Body:
json
Copy code
{
    "name": "John Doe",
    "email": "john@example.com",
    "password": "securepassword"
}
Login User
URL: /api/auth/login
Method: POST
Request Body:
json
Copy code
{
    "email": "john@example.com",
    "password": "securepassword"
}
Response
Successful login will return a JWT token, which should be included in the Authorization header for protected routes.
