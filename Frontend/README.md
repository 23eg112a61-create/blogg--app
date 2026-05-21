> A React-powered frontend for a MERN stack blog platform where users can read, write, and manage articles.

 *Live App:*https://mern-assignments-emt9.vercel.app
 *Backend API:*https://mern-assignments-1-dih8.onrender.com


##  Tech Stack

| Technology          | Purpose                      |
| React               | UI library                   |
| React Router DOM    | Client-side page routing     |
| Axios               | HTTP requests to backend API |
| CSS / Inline styles | Styling                      |

##  Features

-  User registration and login
-  Browse and read articles
-  Authors can write, edit, and delete their articles
-  Admin dashboard for managing users and content
-  Protected routes — only logged-in users can access certain pages

## Folder Structure

Blogapp_frontend/
├── public/
├── src/
│   ├── components/
│   │   ├── Header.jsx          # Navbar shown on all pages
│   │   ├── Footer.jsx          # Footer shown on all pages
│   │   ├── ProtectedRoute.jsx  # Redirects unauthenticated users
│   │   └── ErrorBoundary.jsx   # Catches and handles crashes
│   ├── pages/
│   │   ├── Home.jsx            # Landing page with article feed
│   │   ├── Login.jsx           # User login
│   │   ├── Register.jsx        # User registration
│   │   ├── ArticleByID.jsx     # Single article view
│   │   ├── WriteArticle.jsx    # Create / edit article (authors only)
│   │   ├── AuthorDashboard.jsx # Author's personal dashboard
│   │   ├── AuthorProfile.jsx   # Public author profile page
│   │   ├── AuthorArticles.jsx  # Articles by a specific author
│   │   └── AdminDashboard.jsx  # Admin panel (admin only)
│   ├── layouts/
│   │   └── RootLayout.jsx      # Wraps all pages with Header & Footer
│   ├── App.jsx                 # Route definitions
│   └── main.jsx                # App entry point
├── .env                        # Environment variables (not committed)
├── .gitignore
├── package.json
└── vite.config.js / index.html


##  Getting Started

### Prerequisites

- Node.js installed
- Backend server running (locally or on Render)

### Installation

# Clone the repository
git clone <your-repo-url>
cd Blogapp_frontend

# Install dependencies
npm install

### Environment Variables

Create a .env file in the root:

REACT_APP_API_URL=https://mern-assignments-1-dih8.onrender.com


### Start the App

npm start


##  Architecture

User (Browser)
      │
      ▼
  React App  ──  Vercel (deployed)
      │
      ├── React Router ──▶️ Page Components
      │                        ├── Home.jsx
      │                        ├── Login.jsx / Register.jsx
      │                        ├── ArticleByID.jsx
      │                        ├── WriteArticle.jsx
      │                        ├── AuthorDashboard.jsx
      │                        └── AdminDashboard.jsx
      │
      ├── Axios HTTP Requests (GET / POST / PUT / DELETE)
      │
      ▼
  Express Server (Backend)  ──  Render (deployed)
      │
      ├── /api/auth/login
      ├── /api/auth/register
      ├── /api/articles
      └── /api/users
      │
      ▼
  MongoDB Database
      ├── Users Collection
      └── Articles Collection


##  Component Flow

RootLayout.jsx  (wraps everything)
      │
      ├── Header.jsx               ← Navbar on all pages
      │
      ├── ProtectedRoute.jsx
      │       ├── (logged in)  ──▶️ AuthorDashboard / AdminDashboard / WriteArticle
      │       └── (not logged in) ──▶️ redirect to Login.jsx
      │
      ├── Public Pages
      │       ├── Home.jsx ──▶️ ArticleByID.jsx
      │       ├── Login.jsx / Register.jsx
      │       └── AuthorProfile.jsx ──▶️ AuthorArticles.jsx
      │
      ├── Footer.jsx               ← Footer on all pages
      │
      └── ErrorBoundary.jsx        ← Catches any crashes

##  Deployment

This frontend is deployed on vercel

 *Live URL:*https://mern-assignments-emt9.vercel.app

### Vercel Deployment Notes

- Set environment variables in the Vercel dashboard under *Settings → Environment Variables*.
- Vercel automatically redeploys on every push to your connected branch.
- Make sure REACT_APP_API_URL points to your live Render backend URL.