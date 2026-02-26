# Virtual AI Assistance

This repository contains a MERN stack application for creating a virtual assistant with customizable name and image. The frontend is built with React (Vite) and the backend uses Express with MongoDB.

## Features

- User authentication (signup, signin, logout)
- Choose or upload an assistant image from provided assets
- Set an assistant name and save to profile
- Chat interface with message history stored on the server
- Simple file upload to Cloudinary for custom images

## Project Structure

```
Backend/
  index.js            # Express server entry point
  config/             # DB, cloudinary, token helpers
  controllers/        # Auth and user logic
  middlewares/        # Authorization and multer
  models/             # Mongoose schemas
  routes/             # API endpoints

Frontend/
  src/
    components/       # Reusable components (Card)
    context/          # UserContext provider
    pages/            # Route pages (SignUp, SignIn, Customize, Customize2, Home)
    assets/           # Images used for assistant selection
    App.jsx           # Router configuration
    main.jsx          # Application bootstrap

```

## Getting Started

### Backend

1. Copy `.env.example` to `.env` and fill in:
   ```
   MONGODB_URL=<your MongoDB connection string>
   JWT_SECRET=<your jwt secret>
   CLOUDINARY_CLOUD_NAME=<cloud name>
   CLOUDINARY_API_KEY=<api key>
   CLOUDINARY_API_SECRET=<api secret>
   ```

2. Install dependencies and start server:
   ```bash
   cd Backend
   npm install
   npm run dev    # or npm start
   ```

   Server listens on `http://localhost:8000` by default.

### Frontend

1. Install dependencies and run development server:
   ```bash
   cd Frontend
   npm install
   npm run dev
   ```

   Frontend runs at `http://localhost:5173` and proxies API calls to backend.

2. Visit `http://localhost:5173` to use the app.

## Notes

- The backend uses CORS to allow requests from the frontend origin.
- Uploaded images are sent to Cloudinary and a secure URL is stored in the user document.
- When selecting an asset image, the client sends the asset URL to the backend so the frontend can display it directly.
- Message history is persisted in the MongoDB user document under `history`.

## Development Tips ⚙️

- Make sure MongoDB is running and accessible.
- Use browser devtools to inspect network requests and ensure cookies are sent (`withCredentials: true`).
- You can tweak styling in the frontend using Tailwind utility classes.

Enjoy building your virtual AI assistant! 🧠🤖
