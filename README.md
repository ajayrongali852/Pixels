# 📷 Pixels — Full-Stack Social Media Platform

[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-4.x-000000?logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Material--UI](https://img.shields.io/badge/Material--UI-v5-007FFF?logo=mui&logoColor=white)](https://mui.com/)
[![Redux-Toolkit](https://img.shields.io/badge/Redux-Toolkit-764ABC?logo=redux&logoColor=white)](https://redux-toolkit.js.org/)

**Pixels** is a modern, responsive full-stack social media web application built with the MERN stack (MongoDB, Express, React, Node.js). It offers a rich user experience featuring user authentication, post creation with image uploads, dynamic feed updates, a friend management system, user profile customization, and dark/light theme switching.

---

## ✨ Features

- **Authentication & Security**: Secure registration and login using JSON Web Tokens (JWT) and bcrypt password hashing.
- **Dark / Light Mode**: Seamless theme switching with persistent preferences via Material-UI and Redux.
- **Media Uploads**: Seamless image uploads powered by Multer.
- **Social Feed & Posts**: Create text/image posts, like/unlike posts in real time, and view aggregate likes.
- **Friend Connections**: Add and remove friends with immediate state updates across widgets.
- **User Profiles**: Dedicated user profile views showcasing profile picture, friend count, bio, impressions, and user-specific posts.
- **State Management**: Predictable global state management using Redux Toolkit with persistent storage via `redux-persist`.
- **Responsive Layout**: Designed for mobile, tablet, and desktop screens with custom Material-UI components.

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: React 18
- **UI & Styling**: Material-UI (MUI v5), Emotion
- **State Management**: Redux Toolkit, Redux Persist
- **Form Handling & Validation**: Formik, Yup
- **File Uploads**: React Dropzone
- **Routing**: React Router DOM v6

### Backend
- **Runtime**: Node.js
- **Web Framework**: Express.js (ES Modules)
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT (`jsonwebtoken`), `bcrypt`
- **File Handling**: Multer
- **Security & Utilities**: Helmet, Morgan, CORS, Dotenv

---

## 📁 Project Structure

```text
Pixels/
├── client/                     # Frontend React Application
│   ├── public/                 # Static assets, icons, and index.html
│   └── src/
│       ├── components/         # Reusable UI widgets (FlexBetween, Friend, UserImage, WidgetWrapper)
│       ├── scenes/             # App views & pages
│       │   ├── homePage/       # Home feed scene
│       │   ├── loginPage/      # Login and register scene
│       │   ├── navbar/         # Navigation bar with dark mode toggle
│       │   ├── profilePage/    # User profile scene
│       │   └── widgets/        # Modular dashboard widgets (Posts, FriendList, UserWidget, etc.)
│       ├── state/              # Redux slices and state management
│       ├── App.js              # Root router and MUI theme provider
│       ├── index.js            # React entry point with Redux Persist provider
│       └── theme.js            # Custom color palette and typography settings
├── server/                     # Backend Express REST API
│   ├── controllers/            # Controller logic (auth, posts, users)
│   ├── data/                   # Initial sample dataset for database seeding
│   ├── middleware/             # Authorization middleware (verifyToken)
│   ├── models/                 # Mongoose data models (User, Post)
│   ├── public/assets/          # Server static file storage for uploads and assets
│   ├── routes/                 # API route declarations (auth, posts, user)
│   └── index.js                # Server entry point, database connection & middleware
├── .gitattributes              # Git line endings configuration
├── .gitignore                  # Comprehensive Git ignore rules
└── README.md                   # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your machine:
- [Node.js](https://nodejs.org/) (v16.x or later recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- A [MongoDB Atlas](https://www.mongodb.com/atlas/database) account or a local MongoDB database instance

---

### Backend Setup

1. **Navigate to the server directory**:
   ```bash
   cd server
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure Environment Variables**:
   Copy `.env.example` to create `.env`:
   ```bash
   cp .env.example .env
   ```
   Update `.env` with your values:
   ```env
   PORT=3001
   MONGO_URL=your_mongodb_connection_string
   JWT_SECRET=your_secret_jwt_key
   ```

4. **Start the server**:
   ```bash
   npm start
   ```
   *The server will run on `http://localhost:3001`.*

---

### Frontend Setup

1. **Navigate to the client directory**:
   ```bash
   cd client
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Start the development server**:
   ```bash
   npm start
   ```
   *The client will open in your browser at `http://localhost:3000`.*

---

## 🔌 API Endpoints Reference

### Authentication
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/auth/register` | Register a new user with profile image upload |
| `POST` | `/auth/login` | Authenticate user credentials and return JWT token |

### Users
| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/user/:id` | Fetch user profile data |
| `GET` | `/user/:id/friends` | Fetch user's friends list |
| `PATCH` | `/user/:id/:friendId` | Add or remove a friend |

### Posts
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/posts` | Create a new post with image upload |
| `GET` | `/posts` | Fetch all posts for the main feed |
| `GET` | `/posts/:userId/posts` | Fetch posts by a specific user |
| `PATCH` | `/posts/:id/like` | Like or unlike a post |

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page or submit a pull request.

---

## 📄 License

This project is licensed under the [ISC License](https://opensource.org/licenses/ISC).
