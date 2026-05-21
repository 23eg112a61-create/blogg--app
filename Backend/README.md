# Backend Development

> A Node.js + Express REST API backend connected to MongoDB, deployed on Render.

 *Live URL:* https://mern-assignments-1-dih8.onrender.com


## Tech Stack

- *Runtime:* Node.js
- *Framework:* Express.js
- *Database:* MongoDB (via Mongoose)
- *Environment:* dotenv
- *Dev Tool:* Nodemon


##  Getting Started

### Prerequisites

- Node.js installed
- MongoDB connection string (local or Atlas)

### Installation

# Clone the repository
git clone <your-repo-url>
cd <project-folder>

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env   # then fill in your values

# Start the development server
npm run dev

##  Project Setup Steps

### 1. Initialize Git Repository
git init

> Creates a hidden .git folder that tracks all your changes.


### 2. Add .gitignore

Create a .gitignore file in the root and add:

node_modules/
.env

### 3. Set Up Environment Variables

Create a .env file in the root folder and install dotenv to read values in code:

npm install dotenv

Example .env:

env
PORT=5000
MONGO_URI=your_mongodb_connection_string

### 4. Generate package.json

npm init -y

> Update main to server.js and type to module in the generated file.

### 5. Create Express Application
npm install express


### 6. Connect to Database

npm install mongoose

### 7. Add Middlewares

- Body parsers
- Error handlers

### 8. Design Schemas & Models

Define Mongoose schemas and create models for all your resources.

### 9. Design REST APIs

Build RESTful endpoints for all resources following standard HTTP methods (GET, POST, PUT, DELETE).

##  Running the Server

# Development (with auto-restart)
npm run dev

# Install nodemon (if not already)
npm install -D nodemon

Add this to your package.json scripts:

"scripts": {
  "dev": "nodemon server.js",
  "start": "node server.js"
}

##  Deployment

This backend is deployed on *[Render](https://render.com)*.

 *Live API URL:* https://mern-assignments-1-dih8.onrender.com

> Replace the URL above with your actual Render deployment URL.

### Render Deployment Notes

- Set all environment variables in the Render dashboard under *Environment*.
- Use npm start as the start command.
- Render automatically redeploys on every push to your connected branch.

### Folder Structure

Blogapp_backend/
├── APIs/
│   ├── AdminAPI.js        # Admin-related routes
│   ├── AuthorAPI.js       # Author-related routes
│   ├── commonAPI.js       # Shared/common routes
│   └── UserAPI.js         # User-related routes
├── config/
│   ├── cloudinary.js      # Cloudinary connection setup
│   ├── cloudinaryUpload.js # Image upload configuration
│   └── multer.js          # File upload middleware (multer)
├── middlewares/
│   ├── checkAuthor.js     # Verify if user is an author
│   └── verifyToken.js     # JWT token verification
├── Models/
│   ├── articleModel.js    # Article schema & model
│   └── userModel.js       # User schema & model
├── Services/              # Business logic / helper services
├── node_modules/
├── .env                   # Environment variables (not committed)
├── .gitignore
├── package.json
├── package-lock.json
├── req.http               # API test requests
└── server.js              # App entry point



### Backend development

1. create git repo
     git init

2. Add .gitignore file

3. create .env file for environment variables & read data from
    .env with "dotenv" module
                -npm i dotenv

4. Generate package.json
            -npm init -y

5. Create Express Application
            -npm install express

6. connect to the database
            -npm i mongoose

7. Add middlewares(body parser , error handling middleware)

8. Design Schemas and create models

9. design REST APIs for the all resources
