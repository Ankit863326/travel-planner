# Travel Planner & Booking Hub - Full Stack Application

## Overview
A comprehensive full-stack travel planning and booking platform built with React, Express.js, MongoDB, and Redux. Features complete user authentication, destination management, booking system, reviews, and newsletter functionality.

## Project Type
- **Full-Stack Application**: React frontend + Express.js backend
- **Database**: MongoDB Atlas (cloud database)
- **State Management**: Redux Toolkit with Redux Persist
- **Authentication**: JWT-based with bcrypt password hashing

## Tech Stack

### Frontend
- **React** 18.2.0 with React Router DOM
- **Redux Toolkit** for state management
- **Axios** for API calls
- **React Toastify** for notifications
- **Formik & Yup** for form handling and validation
- **Leaflet & React-Leaflet** for interactive maps
- **Framer Motion** & AOS for animations

### Backend
- **Express.js** 5.1.0 REST API
- **Mongoose** 8.19.4 for MongoDB ODM
- **JWT** for authentication
- **Bcrypt** for password hashing
- **Helmet** for security headers
- **Morgan** for logging
- **Express Rate Limit** for API rate limiting
- **CORS** for cross-origin requests

## Project Structure
```
├── server/
│   ├── config/         # Database configuration
│   ├── controllers/    # Route controllers (auth, destinations, bookings, reviews, newsletter)
│   ├── middleware/     # Auth middleware, error handlers
│   ├── models/         # Mongoose models (User, Destination, Booking, Review, Newsletter)
│   ├── routes/         # API routes
│   ├── utils/          # Utilities (JWT generation, seed data)
│   └── server.js       # Express server entry point
├── src/
│   ├── components/     # Reusable UI components
│   │   ├── Navbar/
│   │   ├── Home/
│   │   ├── Main/
│   │   ├── Footer/
│   │   ├── DestinationCard/
│   │   └── SearchFilters/
│   ├── pages/          # Page components
│   │   ├── Auth/       # Login & Register
│   │   └── Destinations/
│   ├── services/       # API service layer
│   ├── store/          # Redux store and slices
│   ├── App.js
│   └── index.js
└── package.json
```

## Development Configuration
- **Frontend Port**: 5000 (Replit webview)
- **Backend Port**: 3001 (localhost)
- **Host**: 0.0.0.0 (frontend), localhost (backend)
- **Concurrent Servers**: Both frontend and backend run simultaneously

## Database Setup (IMPORTANT)
**MongoDB Atlas Configuration Required:**

1. Your MongoDB Atlas cluster needs to whitelist Replit's IP addresses
2. In MongoDB Atlas dashboard:
   - Navigate to Network Access
   - Click "Add IP Address"
   - Select "Allow Access from Anywhere" (`0.0.0.0/0`)
   - This is required because Replit uses dynamic IP addresses

3. Environment Variables (already configured in Replit Secrets):
   - `MONGODB_URI`: Your MongoDB Atlas connection string
   - `JWT_SECRET`: Secret key for JWT token generation

## API Endpoints

### Authentication (`/api/auth`)
- `POST /register` - Register new user
- `POST /login` - User login
- `GET /profile` - Get user profile (protected)
- `PUT /profile` - Update user profile (protected)

### Destinations (`/api/destinations`)
- `GET /` - Get all destinations (with filters)
- `GET /featured` - Get featured destinations
- `GET /:id` - Get destination by ID
- `POST /` - Create destination (admin only)
- `PUT /:id` - Update destination (admin only)
- `DELETE /:id` - Soft delete destination (admin only)

### Bookings (`/api/bookings`)
- `POST /` - Create booking (protected)
- `GET /my-bookings` - Get user bookings (protected)
- `GET /all` - Get all bookings (admin only)
- `GET /:id` - Get booking by ID (protected)
- `PUT /:id/status` - Update booking status (protected)

### Reviews (`/api/reviews`)
- `POST /` - Create review (protected)
- `GET /destination/:destinationId` - Get destination reviews
- `PUT /:id/approve` - Approve review (admin only)
- `DELETE /:id` - Delete review (protected)

### Newsletter (`/api/newsletter`)
- `POST /subscribe` - Subscribe to newsletter
- `POST /unsubscribe` - Unsubscribe from newsletter
- `GET /subscribers` - Get all subscribers (admin only)

## Recent Changes
- **2025-11-16**: Full-stack application development
  - Created complete Express.js backend with RESTful API
  - Implemented MongoDB models for all entities
  - Built Redux state management with auth, destinations, bookings slices
  - Created authentication pages (Login, Register)
  - Developed destinations listing with filtering
  - Integrated React Router for navigation
  - Configured concurrent frontend/backend servers
  - Added comprehensive API service layer
  - Implemented JWT authentication with bcrypt
  - Added security middleware (helmet, CORS, rate limiting)

## Current Status
✅ Backend API fully implemented
✅ Frontend architecture with Redux established
✅ Authentication system complete
✅ Destinations listing and filtering
⚠️ MongoDB connection pending (requires Atlas IP whitelist configuration)
⏳ Booking flow in development
⏳ Maps integration pending
⏳ Admin panel pending

## Next Steps
1. Configure MongoDB Atlas IP whitelist (0.0.0.0/0)
2. Seed database with sample destinations
3. Complete booking flow UI
4. Integrate Leaflet maps
5. Build user dashboard
6. Create admin panel

## User Preferences
None documented yet.
