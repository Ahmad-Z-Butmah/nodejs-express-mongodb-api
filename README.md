# Node.js Express MongoDB REST API

A backend REST API project built with Node.js, Express.js, and MongoDB.

The project provides a structured backend foundation for building web and mobile applications, with authentication, authorization, CRUD operations, validation, and database integration.

## Overview

The API provides the main backend functionality required for a typical database-driven application.

The system includes:

* User registration and login
* JWT-based authentication
* Password hashing
* Role-based authorization
* Book management
* CRUD operations
* Request validation
* Standard API responses
* MongoDB database integration
* Email and OTP support
* Postman API collection

## Main Workflows

The authentication and API workflow follows a structured process:

```text
User Registration
        |
        v
Account Verification
        |
        v
User Login
        |
        v
JWT Token Generated
        |
        v
Authenticated API Request
        |
        v
Authorization Middleware
        |
        v
Controller
        |
        v
MongoDB
```

## User Authentication

The API provides basic authentication functionality.

Users can:

* Create an account
* Log in using their credentials
* Verify their account using an OTP
* Receive a JWT authentication token
* Access protected API endpoints
* Use the token with the `Authorization: Bearer <token>` header

Passwords are hashed before being stored in the database.

## Book Management

The project includes a Book module as an example of a database-driven resource.

The API supports:

* Create a book
* View books
* View a specific book
* Update a book
* Delete a book
* Validate book data

The Book module demonstrates how models, controllers, and routes work together.

## API Structure

The backend follows a modular structure separating routes, controllers, models, middleware, and helper functions.

```text
.
├── app.js
├── package.json
├── bin
│   └── www
├── controllers
│   ├── AuthController.js
│   └── BookController.js
├── models
│   ├── BookModel.js
│   └── UserModel.js
├── routes
│   ├── api.js
│   ├── auth.js
│   └── book.js
├── middlewares
│   └── jwt.js
├── helpers
│   ├── apiResponse.js
│   ├── constants.js
│   ├── mailer.js
│   └── utility.js
├── test
│   ├── testConfig.js
│   ├── auth.js
│   └── book.js
└── public
    ├── index.html
    └── stylesheets
        └── style.css
```

## System Architecture

The API follows a simple layered backend architecture:

```text
Client
  |
  v
REST API
  |
  v
Express.js
  |
  +--> Routes
  |
  +--> Middleware
  |
  +--> Controllers
  |
  +--> Models
  |
  v
MongoDB
```

## Backend

The Express.js backend handles:

* HTTP requests and responses
* Authentication
* Authorization
* API routing
* Business logic
* Database operations
* Request validation
* Error and response handling

## Authentication & Authorization

JWT is used to protect authenticated API endpoints.

After successful login, the API returns a JWT token that can be included in subsequent requests.

Protected routes use middleware to verify the token before allowing access to the requested resource.

## Database

MongoDB is used as the project's database.

The application uses models to define and interact with database documents.

Main models include:

* User
* Book

## API Testing

The project includes a Postman API collection for testing the available endpoints.

The API can be tested by sending requests for:

* Authentication
* User operations
* Book CRUD operations
* Protected endpoints

## Validation & Error Handling

The API includes request validation and predefined response structures.

HTTP status codes are used to indicate the result of API operations.

This provides a consistent structure for clients consuming the REST API.

## Testing

The project includes automated tests using:

* Mocha
* Chai

Tests cover authentication and Book API functionality.

Code coverage is also supported through Istanbul/NYC.

Run the tests with:

```bash
npm test
```

## Code Quality

ESLint is included to help maintain consistent JavaScript code quality.

Run linting with:

```bash
npm run lint
```

## Technologies

* Node.js
* Express.js
* JavaScript (ES2015)
* MongoDB
* Mongoose
* JWT
* REST APIs
* Mocha
* Chai
* ESLint
* Postman
* npm

## Environment Configuration

Environment variables are used for sensitive configuration.

Create a `.env` file based on `.env.example`.

Environment variables can be used for:

* MongoDB connection
* JWT secret
* Email configuration
* Application configuration

Sensitive credentials should not be committed to the repository.

## Running the Project

### Install dependencies

```bash
npm install
```

### Configure environment variables

Create a `.env` file from the provided example:

```bash
cp .env.example .env
```

Update the values according to your local environment.

### Start the development server

```bash
npm run dev
```

The API will connect to MongoDB and start the Express.js server.

## Key Features

This project demonstrates:

* Node.js backend development
* Express.js REST API development
* MongoDB database integration
* JWT authentication
* Authorization middleware
* CRUD operations
* Modular backend architecture
* Request validation
* API testing
* Environment configuration
* Basic automated testing

## Project Purpose

The project was developed to practice building a structured REST API using Node.js and Express.js, while applying common backend development concepts such as authentication, database operations, middleware, API routing, and testing.

## Security

Sensitive information should not be committed to the repository.

Environment variables should be used for:

* Database credentials
* JWT secrets
* Email credentials
* External service configuration
