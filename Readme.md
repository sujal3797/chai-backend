# Chai and Backend - A Video Platform API

A fully-featured backend service for a YouTube-like platform, providing RESTful APIs for user management, video uploads, and subscriptions. This project was built to demonstrate a modern backend architecture using Node.js, Express, and MongoDB.

![NodeJS](https://img.shields.io/badge/Node.js-18.x-green.svg) ![Express.js](https://img.shields.io/badge/Express.js-4.x-blue.svg) ![MongoDB](https://img.shields.io/badge/MongoDB-6.x-green.svg) ![JWT](https://img.shields.io/badge/Auth-JWT-orange.svg)

**[Live Demo Link (if available)](http://your-live-api-link.com)**

## Key Features

* **JWT Authentication:** Secure user registration and login with access and refresh tokens.
* **File Uploads:** Handles multipart/form-data for uploading user avatars, cover images, and video files using `multer`.
* **Cloud Integration:** Seamlessly uploads media files to Cloudinary for scalable storage.
* **MongoDB Aggregation Pipelines:** Complex queries for user channel profiles and subscription data.
* **Standardized API Responses:** Consistent and predictable API response structure (`ApiResponse`) and error handling (`ApiError`).

## Tech Stack

* **Backend:** Node.js, Express.js
* **Database:** MongoDB with Mongoose
* **Authentication:** JWT (JSON Web Tokens), bcrypt
* **File Handling:** Multer, Cloudinary for cloud storage
* **Development:** Nodemon, Prettier

## Getting Started

### Prerequisites

* Node.js (v18 or higher)
* npm
* MongoDB instance (local or cloud-based)
* Cloudinary account

### Installation

1.  Clone the repository:
    ```bash
    git clone [https://your-repository-url.com/](https://your-repository-url.com/)
    ```
2.  Install NPM packages:
    ```bash
    npm install
    ```
3.  Create a `.env` file in the root directory and add the necessary environment variables:
    ```env
    MONGODB_URI=<your_mongodb_uri>
    CORS_ORIGIN=*
    ACCESS_TOKEN_SECRET=<your_access_token_secret>
    ACCESS_TOKEN_EXPIRY=1d
    REFRESH_TOKEN_SECRET=<your_refresh_token_secret>
    REFRESH_TOKEN_EXPIRY=10d
    CLOUDINARY_CLOUD_NAME=<your_cloudinary_cloud_name>
    CLOUDINARY_API_KEY=<your_cloudinary_api_key>
    CLOUDINARY_API_SECRET=<your_cloudinary_api_secret>
    ```
4.  Start the development server:
    ```bash
    npm run dev
    ```

## API Endpoints

Here are some of the key API endpoints available.

### User Routes

* `POST /api/v1/users/register` - Register a new user.
    * **Body (multipart/form-data):** `username`, `email`, `password`, `fullName`, `avatar` (file), `coverImage` (file)
* `POST /api/v1/users/login` - Log in a user.
    * **Body (json):** `email` or `username`, `password`
* `POST /api/v1/users/logout` - Log out the currently authenticated user (requires JWT token).
* `GET /api/v1/users/current-user` - Get details of the currently logged-in user (requires JWT token).

## Project Challenges & Key Learnings

Building this project involved several challenges and learning opportunities:

* **Authentication Flow:** Implementing a secure authentication system with both access and refresh tokens was a key challenge. This involved understanding JWT best practices, token expiry, and secure cookie storage.
* **Complex Database Queries:** Designing efficient MongoDB aggregation pipelines for features like the user channel profile, which calculates subscriber counts and subscription status in a single query.
* **Asynchronous File Handling:** Managing the flow of file uploads from the client, temporarily storing them on the server, and then uploading them to a cloud service like Cloudinary required careful handling of asynchronous operations and error management.
