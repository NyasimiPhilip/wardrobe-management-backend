# Wardrobe Management Application

A full-stack web application for managing your wardrobe, built with **Laravel** (backend) and **Vue.js** (frontend).

## Overview

This application allows users to:
- Manage their clothing items
- Organize items by categories
- Track their wardrobe inventory
- Secure authentication system

## Tech Stack

### Backend
- **Laravel 9.x**
- **PHP 8.x**
- **MySQL**
- **Laravel Sanctum** for authentication
- **RESTful API** architecture

### Frontend
- **Vue.js 3.x**
- **Vuex 4.x** for state management
- **Vue Router 4.x**
- **Axios** for API communication
- Modern component-based architecture

## Project Structure

```
wardrobe-management/
├── backend/        # Laravel backend
│   ├── app/
│   │   ├── Http/
│   │   │   ├── Controllers/     # API controllers
│   │   │   └── Requests/        # Form requests
│   │   └── Models/             # Eloquent models
│   ├── database/
│   │   └── migrations/         # Database migrations
│   └── routes/
│       └── api.php            # API routes
└── frontend/       # Vue.js frontend
    ├── src/
    │   ├── components/         # Reusable Vue components
    │   ├── views/              # Page components
    │   ├── store/              # Vuex store modules
    │   ├── router/             # Vue Router configuration
    │   └── services/           # API services
    └── public/                # Static assets
```

## Features

### Authentication
- User registration
- Login/Logout
- Protected routes
- Token-based authentication using Sanctum

### Clothing Management
- Create, read, update, and delete clothing items
- Categorize items
- View all items in inventory

### Category Management
- Create and manage categories
- Organize clothing items by category

## Setup Instructions

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   composer install
   ```
3. Configure environment variables:
   ```bash
   cp .env.example .env
   ```
4. Run migrations:
   ```bash
   php artisan migrate
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd ../frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Run development server:
   ```bash
   npm run dev
   ```

## API Documentation

### Authentication

#### Register User
**Endpoint:**
```
POST /api/register
```
**Request Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```
**Response:**
```json
{
  "message": "User registered successfully",
  "token": "your_generated_token_here"
}
```

#### Login
**Endpoint:**
```
POST /api/login
```
**Request Body:**
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```
**Response:**
```json
{
  "message": "Login successful",
  "token": "your_generated_token_here"
}
```

### Clothing Management

#### Create Clothing Item
**Endpoint:**
```
POST /api/clothing
```
**Request Body:**
```json
{
  "name": "T-shirt",
  "category_id": 1,
  "description": "A comfortable cotton t-shirt"
}
```
**Response:**
```json
{
  "message": "Clothing item created successfully",
  "item": {
    "id": 1,
    "name": "T-shirt",
    "category_id": 1,
    "description": "A comfortable cotton t-shirt"
  }
}
```

#### Get All Clothing Items
**Endpoint:**
```
GET /api/clothing
```
**Response:**
```json
{
  "message": "Clothing items retrieved successfully",
  "items": [
    {
      "id": 1,
      "name": "T-shirt",
      "category_id": 1,
      "description": "A comfortable cotton t-shirt"
    }
  ]
}
```

#### Get Clothing Item by ID
**Endpoint:**
```
GET /api/clothing/{id}
```
**Response:**
```json
{
  "message": "Clothing item retrieved successfully",
  "item": {
    "id": 1,
    "name": "T-shirt",
    "category_id": 1,
    "description": "A comfortable cotton t-shirt"
  }
}
```

#### Update Clothing Item
**Endpoint:**
```
PUT /api/clothing/{id}
```
**Request Body:**
```json
{
  "name": "T-shirt",
  "category_id": 1,
  "description": "A comfortable cotton t-shirt"
}
```
**Response:**
```json
{
  "message": "Clothing item updated successfully",
  "item": {
    "id": 1,
    "name": "T-shirt",
    "category_id": 1,
    "description": "A comfortable cotton t-shirt"
  }
}
```

#### Delete Clothing Item
**Endpoint:**
```
DELETE /api/clothing/{id}
```
**Response:**
```json
{
  "message": "Clothing item deleted successfully"
}
```

### Category Management

#### Create Category
**Endpoint:**
```
POST /api/categories
```
**Request Body:**
```json
{
  "name": "T-shirts"
}
```
**Response:**
```json
{
  "message": "Category created successfully",
  "category": {
    "id": 1,
    "name": "T-shirts"
  }
}
```

#### Get All Categories
**Endpoint:**
```
GET /api/categories
```
**Response:**
```json
{
  "message": "Categories retrieved successfully",
  "categories": [
    {
      "id": 1,
      "name": "T-shirts"
    }
  ]
}
```

#### Delete Category
**Endpoint:**
```
DELETE /api/categories/{id}
```
**Response:**
```json
{
  "message": "Category deleted successfully"
}
```

