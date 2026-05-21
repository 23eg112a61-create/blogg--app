> PenPal is a full-stack MERN blog platform where users can read articles, authors can write and manage their content, and admins can oversee the entire platform.

 *Frontend (Vercel):*https://mern-assignments-emt9.vercel.app
 *Backend API (Render):*https://mern-assignments-1-dih8.onrender.com

## About the App

PenPal is a multi-role blogging platform built with the MERN stack. It supports three types of users:

- *Readers* — browse and read articles without signing up
- *Authors* — register, log in, and publish/manage their own articles
- *Admins* — manage all users and content from a dedicated dashboard

The frontend is built in React and deployed on Vercel. The backend is a REST API built with Express and Node.js, deployed on Render, connected to a MongoDB database.

##  Project Structure

This is a monorepo containing two separate apps:

PenPal/
├── Blogapp_frontend/     # React app → deployed on Vercel
└── Blogapp_backend/      # Express + Node.js API → deployed on Render


##  Tech Stack

| Layer    | Technology | Purpose |
| Frontend | React | UI and user interaction |
| Frontend | React Router DOM | Client-side routing |
| Frontend | Axios | HTTP requests to backend |
| Backend  | Node.js | Runtime environment |
| Backend  | Express.js | REST API framework |
| Backend  | Mongoose | MongoDB ODM |
| Backend  | JWT | Authentication tokens |
| Backend    | Multer + Cloudinary | Image uploads |
| Database | MongoDB | Data storage |
| Deployment | Vercel | Frontend hosting |
| Deployment | Render | Backend hosting |


##  Key Features

-  JWT-based user authentication (register / login / logout)
-  Public article feed — readable without login
-  Authors can create, edit, and delete their own articles
-  Image upload support via Cloudinary
-  Admin dashboard to manage users and content
-  Protected routes — restricted pages redirect unauthenticated users
-  Author profiles with their published articles

##  How It Works

User (Browser)
      │
      ▼
  React App  ──  Vercel
      │
      ├── Public pages  ──▶️  Home, ArticleByID, AuthorProfile
      ├── Auth pages    ──▶️  Login, Register
      └── Protected     ──▶️  WriteArticle, AuthorDashboard, AdminDashboard
      │
      │   Axios HTTP (GET / POST / PUT / DELETE)
      │
      ▼
  Express REST API  ──  Render
      │
      ├── /api/auth      ──▶️  login, register
      ├── /api/articles  ──▶️  CRUD for articles
      └── /api/users     ──▶️  user management
      │
      ▼
  MongoDB
      ├── Users Collection
      └── Articles Collection


##  User Roles

| Role | What they can do |
| Reader | Browse and read all articles |
| Author | Everything above + write, edit, delete own articles |
| Admin | Everything above + manage all users and content |


##  Getting Started (Local Setup)

### 1. Clone the repository

bash
git clone <your-repo-url>
cd PenPal


### 2. Set up the Backend

bash
cd Blogapp_backend
npm install


Create a .env file:

env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret


bash
npm run dev


### 3. Set up the Frontend

bash
cd ../Blogapp_frontend
npm install


Create a .env file:

env
REACT_APP_API_URL=http://localhost:5000


bash
npm start


> Frontend runs on http://localhost:3000 · Backend runs on http://localhost:5000

---

## ☁️ Deployment

| App | Platform | URL |
| Frontend | Vercel | https://mern-assignments-emt9.vercel.app |
| Backend | Render | https://mern-assignments-1-dih8.onrender.com |

- Vercel auto-deploys on every push to the frontend branch
- Render auto-deploys on every push to the backend branch
- Set all .env variables in each platform's dashboard before deploying