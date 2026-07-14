# Wanderlust — Accommodation Listings & Reviews Platform

Wanderlust is a full-stack accommodation listings and reviews platform inspired by modern travel marketplace applications such as Airbnb.

The project was built to practice end-to-end web application development using the MERN ecosystem's backend technologies, server-side rendering with EJS, authentication, authorization, CRUD operations, image uploads, validation, and database modelling.

> **Note:** Wanderlust is **not** a booking or reservation system. The application focuses on accommodation listings, user authentication, and review management.

---

# Live Demo

https://wanderlust-zba2.onrender.com/listings

---

# Demo Account

**Email**

```
demo@gmail.com
```

**Password**

```
demo
```

*(Update these credentials if they change.)*

---

# Project Overview

Managing accommodation listings involves more than simply displaying data. Property owners need a way to create and manage listings, upload images, and receive reviews, while visitors need an intuitive interface to browse listings and share feedback.

Wanderlust demonstrates how these workflows can be implemented in a traditional server-rendered web application using Node.js, Express.js, MongoDB, Passport.js, and EJS.

---

# Objectives

This project was built to gain practical experience with:

- MVC architecture
- Server-side rendering
- CRUD operations
- MongoDB data modelling
- User authentication
- Authorization
- Image uploads
- Form validation
- Interactive maps
- Session management
- Error handling

---

# Features

## User Authentication

- User registration
- User login
- User logout
- Password hashing
- Session-based authentication using Passport.js

---

## Authorization

- Users can only edit their own listings.
- Users can only delete their own listings.
- Users can only delete reviews they created.

---

## Listings

- Create listings
- Edit listings
- Delete listings
- Browse all listings
- View listing details

---

## Reviews

- Add reviews
- Delete reviews
- Rating system

---

## Images

- Upload listing images
- Cloudinary image hosting
- Multer upload middleware

---

## Maps

- Display listing locations using Mapbox

---

## Validation

- Joi server-side validation
- Flash messages
- Error handling middleware

---

# Tech Stack

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- Passport.js (Local Strategy)
- Express Session
- Connect-Mongo
- Joi

---

## Frontend

- EJS
- Bootstrap
- HTML
- CSS
- JavaScript

---

## Third-Party Services

- Cloudinary
- Mapbox

---

# Architecture

The project follows the MVC (Model–View–Controller) architecture.

```
Browser
   │
   ▼
Express Routes
   │
   ▼
Controllers
   │
   ▼
Models (Mongoose)
   │
   ▼
MongoDB
```

Project responsibilities are separated into:

- Models
- Views
- Controllers
- Routes
- Middleware
- Utilities

---

# Project Structure

```text
├── controllers/
├── middleware/
├── models/
├── public/
├── routes/
├── utils/
├── views/
├── app.js
├── cloudConfig.js
├── schema.js
└── package.json
```

---

# Authentication Flow

```
User
   │
Register/Login
   │
Passport Local Strategy
   │
Session Created
   │
Express Session
   │
Mongo Session Store
   │
Authenticated Requests
```

Authentication uses:

- Passport.js
- Express Session
- Connect-Mongo

This project uses **session-based authentication**, not JWT.

---

# Data Models

Main collections include:

- Users
- Listings
- Reviews

Relationships:

- A user owns many listings.
- A listing contains multiple reviews.
- Each review belongs to a user.

---

# Validation

Validation is performed using:

- Joi schemas
- Middleware
- Mongoose validation
- Flash messages

This prevents invalid data from reaching the database.

---

# Image Upload Workflow

```
Browser

↓

Multer

↓

Cloudinary

↓

Image URL stored in MongoDB
```

---

# Map Integration

Mapbox is used to display listing locations.

Listings store location information which is rendered on interactive maps.

---

# Running Locally

Clone the repository.

```bash
git clone https://github.com/yadavkapil-dev/Wanderlust.git
```

Install dependencies.

```bash
npm install
```

Start the application.

```bash
npm start
```

---

# Environment Variables

Create a `.env` file.

```ini
ATLASDB_URL=

CLOUD_NAME=

CLOUD_API_KEY=

CLOUD_API_SECRET=

MAP_TOKEN=

SECRET=
```

---

# What I Learned

Through this project I gained practical experience with:

- MVC architecture
- Express.js routing
- MongoDB data modelling
- Passport.js authentication
- Session management
- Authorization middleware
- Cloudinary integration
- File uploads using Multer
- Mapbox integration
- Joi validation
- Server-side rendering with EJS
- Error handling
- CRUD application design

---

# Current Limitations

This project focuses on accommodation listings and reviews.

The following features are **not implemented**:

- Reservation or booking workflow
- Payment processing
- Availability calendar
- Customer messaging
- Notifications
- Docker
- CI/CD pipelines
- Automated tests
- CSRF protection
- Rate limiting
- Helmet/CSP configuration
- Automatic Cloudinary asset cleanup
- Multi-tenant architecture

---

# Future Improvements

Potential future enhancements include:

- Reservation system
- Booking management
- Payment integration
- Availability calendar
- Advanced search and filtering
- Wishlist functionality
- Email notifications
- Docker containerization
- CI/CD pipeline
- Automated testing
- Stronger security hardening
- Improved image lifecycle management

---

# Resume-Safe Project Summary

Wanderlust is a full-stack accommodation listings and reviews platform built using Node.js, Express.js, MongoDB, Passport.js, and EJS.

The application demonstrates user authentication, authorization, CRUD operations, image uploads with Cloudinary, interactive maps using Mapbox, server-side rendering, and MongoDB data modelling.

It is **not** a booking or payment platform, and no reservation workflow has been implemented.

---

# License

This project was built for learning purposes and to demonstrate full-stack software engineering concepts.
