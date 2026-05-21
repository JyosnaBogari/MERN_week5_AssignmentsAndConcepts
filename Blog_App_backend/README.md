Blog App Backend
A secure and scalable backend API for the Blog App built using Node.js, Express.js, MongoDB Atlas, JWT authentication, Cloudinary image storage, and role-based authorization.

This backend powers the complete blog platform including authentication, user management, article management, admin controls, and image uploads.

Live API
Backend Deployment:
https://blog-app-project-pq3x.onrender.com

Frontend Application:
https://blog-app-project-eight.vercel.app

GitHub Repository:
https://github.com/JyosnaBogari/Blog-App-Project

Features
Authentication & Security
JWT-based authentication
Cookie-based session management
Password hashing using bcryptjs
Role-based access control
Protected API routes
Secure logout functionality
Authentication persistence
Unauthorized request blocking
User Features
User registration
User login
Fetch all active articles
View single article details
View author profiles
Update profile
Change password
Author Features
Author registration
Login
Create blog articles
Upload article images
Edit own articles
View authored articles
Update article publishing status
Admin Features
View all users
Block users
Unblock users
View all articles
Activate articles
Deactivate articles
Full moderation access
Backend Functionalities
REST API architecture
MongoDB database integration
Mongoose schema validation
Middleware-based authentication
Centralized error handling
Cloudinary image uploads
Multer file handling
CORS configuration
Environment variable configuration
Tech Stack
Backend Technologies
Node.js
Express.js
MongoDB Atlas
Mongoose
JWT
bcryptjs
cookie-parser
CORS
dotenv
Multer
Cloudinary
Project Structure
backend/
│
├── APIs/
│   ├── AdminAPI.js
│   ├── AuthorAPI.js
│   ├── CommonAPI.js
│   └── UserAPI.js
│
├── config/
│   ├── cloudinary.js
│   └── multer.js
│
├── middlewares/
│   └── verifyToken.js
│
├── models/
│   ├── ArticleModel.js
│   └── UserModel.js
│
├── services/
│
├── server.js
├── package.json
├── package-lock.json
└── README.md
Prerequisites

Install the following before running backend.

1. Node.js

Download:

https://nodejs.org/

Verify:

node -v
npm -v
2. Git

Download:

https://git-scm.com/

Verify:

git --version
3. MongoDB Atlas Account

Create account:

https://www.mongodb.com/cloud/atlas

Required for database hosting.

4. Cloudinary Account

Create account:

https://cloudinary.com/

Required for article image uploads.

Installation

Clone repository:

git clone https://github.com/JyosnaBogari/Blog-App-Project.git

Move into backend:

cd Blog-App-Project/backend

Install dependencies:

npm install
Required Packages

Installed automatically with npm install:

express
mongoose
jsonwebtoken
bcryptjs
cookie-parser
cors
dotenv
multer
cloudinary
Environment Variables

Create .env file inside backend folder.

Example:

DB_URL=your_mongodb_atlas_connection_string
PORT=4000
JWT_SECRET=your_secure_jwt_secret
CLOUD_NAME=your_cloudinary_cloud_name
API_KEY=your_cloudinary_api_key
API_SECRET=your_cloudinary_api_secret
NODE_ENV=development
MongoDB Atlas Setup
Step 1

Create MongoDB Atlas account:

https://www.mongodb.com/cloud/atlas

Step 2

Create a new cluster

Choose free tier.

Step 3

Create database user

Set:

username
password
Step 4

Network Access

Allow:

0.0.0.0/0

for development.

Step 5

Get connection string

Example:

mongodb+srv://username:password@cluster.mongodb.net/blogdb

Paste in:

DB_URL=
Cloudinary Setup
Step 1

Create account:

https://cloudinary.com/

Step 2

Copy credentials:

Dashboard provides:

Cloud Name
API Key
API Secret
Step 3

Add to .env

CLOUD_NAME=
API_KEY=
API_SECRET=
Running Backend Locally

Start server:

node server.js

Expected output:

DB connection success
server started on port 4000
API Base URL

Local:

http://localhost:4000

Production:

https://blog-app-project-pq3x.onrender.com
API Endpoints
Common Routes
Login
POST /common-api/login
Logout
GET /common-api/logout
Change Password
PUT /common-api/change-password
Check Authentication
GET /common-api/check-auth
User Routes
Register User
POST /user-api/users
Get All Articles
GET /user-api/articles
Update User Article Interaction
PUT /user-api/articles
Get Single Article
GET /user-api/article/:id
Author Routes
Register Author
POST /author-api/users
Create Article
POST /author-api/articles
Get Author Articles
GET /author-api/articles/:authorId
Update Article
PUT /author-api/articles
Change Article Status
PATCH /author-api/articles/:id/status
Admin Routes
Get All Articles
GET /admin-api/articles
Get All Users
GET /admin-api/users
Block User
PUT /admin-api/users/block/:userId
Unblock User
PUT /admin-api/users/unblock/:userId
Activate Article
PUT /admin-api/articles/activate/:articleId
Deactivate Article
PUT /admin-api/articles/deactivate/:articleId
Authentication Flow

This backend uses cookie-based JWT authentication.

Flow:

User sends login credentials
Backend validates user
Password checked using bcryptjs
JWT token generated
Token stored in cookies
Protected routes verify token
Role determines access

Roles:

USER
AUTHOR
ADMIN
Middleware
CORS

Configured for:

http://localhost:5173
https://blog-app-project-eight.vercel.app
Cookie Parser

Used for reading authentication cookies.

Express JSON Parser

Parses incoming JSON request bodies.

verifyToken Middleware

Protects secured routes.

Validates:

JWT token
user authentication
role access
Error Handling

Centralized error middleware handles:

Validation errors
Invalid routes
MongoDB duplicate errors
Cast errors
Strict mode errors
Unexpected server errors
Deployment on Render
Step 1

Push code to GitHub

git add .
git commit -m "backend deployment"
git push
Step 2

Open:

https://render.com

Step 3

Create Web Service

Step 4

Connect GitHub repository:

JyosnaBogari/Blog-App-Project
Step 5

Configure

Root Directory:

backend

Build Command:

npm install

Start Command:

node server.js
Step 6

Add Environment Variables

DB_URL=
PORT=4000
JWT_SECRET=
CLOUD_NAME=
API_KEY=
API_SECRET=
NODE_ENV=production
Step 7

Deploy

Render will provide backend URL.

Troubleshooting
MongoDB Connection Error

Check:

DB_URL

Ensure:

correct username
correct password
network access enabled
Cloudinary Upload Error

Check:

CLOUD_NAME
API_KEY
API_SECRET
CORS Error

Ensure frontend URL exists in CORS config.

JWT Authentication Error

Check:

JWT_SECRET
cookie settings
login flow
Render Deployment Fails

Check:

root directory = backend
environment variables
start command
Future Improvements
Search API
Blog comments
Likes system
Email verification
Password reset
Notifications
Analytics dashboard
Rich text editor support
Article categories
Pagination
Author

Jyosna Bogari

B.Tech IT Student | MERN Stack Developer

GitHub:
https://github.com/JyosnaBogari
