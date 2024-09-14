# rbac-system
Role-Based Access Control (RBAC) System
This project implements a basic Role-Based Access Control (RBAC) system using Node.js, Express, and MongoDB. It includes user registration, login, authentication using JWT, and role-based access control for protected routes.

Features
User authentication (login and registration) using JSON Web Tokens (JWT)
Role-based access control (admin, user, etc.)
Protected routes based on user roles
Middleware for error handling (401 Unauthorized, 403 Forbidden)
Logging of user role and access status for each request
REST API endpoints for user management, including role updates
Prerequisites
Before you begin, make sure you have the following installed on your machine:

Node.js (version 12.x or higher)
MongoDB (running locally or cloud instance)
Git
Getting Started
Follow these instructions to set up and run the project locally.

1. Clone the Repository
First, clone the repository to your local machine:

bash
Copy code
git clone https://github.com/jyotilaxmi98/rbac-system.git
cd rbac-system
2. Install Dependencies
After cloning the repository, install the necessary dependencies:

bash
Copy code
npm install
3. Environment Setup
Create a .env file in the root directory of the project and add the following configuration settings:

bash
Copy code
PORT=5000
MONGODB_URI=mongodb://localhost:27017/rbac-system
JWT_SECRET=your_jwt_secret_key
Replace MONGODB_URI with your MongoDB connection string if running a remote instance.
Replace JWT_SECRET with a secure key for JWT signing.
4. Run MongoDB
Ensure your MongoDB server is running locally, or have access to a remote MongoDB instance.

bash
Copy code
# Run MongoDB locally (if using local setup)
mongod
5. Start the Application
Start the Node.js server:

bash
Copy code
npm start
The server will start on the port specified in your .env file (default: 5000).

6. Access the Application
API base URL: http://localhost:5000/
Use tools like Postman or cURL to interact with the API.

API Endpoints
1. User Registration
http
Copy code
POST /api/register
Payload:

json
Copy code
{
  "username": "your_username",
  "password": "your_password",
  "role": "user" // Default role is user
}
2. User Login
http
Copy code
POST /api/login
Payload:

json
Copy code
{
  "username": "your_username",
  "password": "your_password"
}
3. Protected Route Example
http
Copy code
GET /api/admin
Only accessible by users with the admin role.
Attach the JWT token in the Authorization header as Bearer token.
4. Update User Role
http
Copy code
PATCH /api/users/:id/role
Accessible only by admin users to update the roles of other users.
Error Handling
401 Unauthorized: Invalid or missing token.
403 Forbidden: User does not have sufficient permissions.
Logging
Each request to a protected route logs the user's role and access status.


