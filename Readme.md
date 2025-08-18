# VideoTube - A Video Platform API

![NodeJS](https://img.shields.io/badge/Node.js-18.x-green.svg) ![Express.js](https://img.shields.io/badge/Express.js-5.x-blue.svg) ![MongoDB](https://img.shields.io/badge/MongoDB-6.x-green.svg) ![JWT](https://img.shields.io/badge/Auth-JWT-orange.svg)

A complete, production-ready backend service for a modern video-sharing platform, similar to YouTube. This project provides a robust and secure RESTful API for user management, authentication, and channel subscriptions.

**Live Demo:** [https://chai-backend-1-etao.onrender.com](https://chai-backend-1-etao.onrender.com)

## Key Features

* **Secure JWT Authentication:** Implements a full authentication system using JSON Web Tokens (JWT) with both access and refresh tokens for enhanced security.
* **Cloud Media Management:** Integrates with **Cloudinary** for scalable, cloud-based storage and management of user avatars and cover images.
* **Robust File Handling:** Uses **Multer** to handle `multipart/form-data`, allowing for efficient and secure file uploads.
* **Advanced Database Queries:** Leverages **MongoDB Aggregation Pipelines** for complex data retrieval, such as fetching detailed user channel profiles with subscriber counts.
* **Secure Password Management:** Uses **bcrypt** to hash and salt user passwords, ensuring they are never stored in plain text.
* **Standardized API Responses:** Employs custom `ApiResponse` and `ApiError` classes to ensure consistent and predictable API responses and error handling.

## Tech Stack

* **Backend:** Node.js, Express.js
* **Database:** MongoDB with Mongoose
* **Authentication:** JWT (jsonwebtoken), bcrypt
* **File Handling:** Multer, Cloudinary
* **Development:** Nodemon for hot-reloading, Prettier for code formatting.

## Getting Started

### Prerequisites

* Node.js (v18 or higher)
* npm
* MongoDB instance (local or cloud-based)
* Cloudinary account

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    ```
2.  **Install NPM packages:**
    ```bash
    npm install
    ```
3.  **Create a `.env` file** in the root directory and add the following environment variables:
    ```env
    MONGODB_URI=<your_mongodb_uri>
    DB_NAME=videotube
    CORS_ORIGIN=*
    ACCESS_TOKEN_SECRET=<your_access_token_secret>
    ACCESS_TOKEN_EXPIRY=1d
    REFRESH_TOKEN_SECRET=<your_refresh_token_secret>
    REFRESH_TOKEN_EXPIRY=10d
    CLOUDINARY_CLOUD_NAME=<your_cloudinary_cloud_name>
    CLOUDINARY_API_KEY=<your_cloudinary_api_key>
    CLOUDINARY_API_SECRET=<your_cloudinary_api_secret>
    ```
4.  **Start the development server:**
    ```bash
    npm run dev
    ```

## API Endpoints

The API is versioned under the `/api/v1` prefix.

### User & Authentication Routes

* `POST /api/v1/users/register` - Register a new user.
    * **Body (multipart/form-data):** `username`, `email`, `password`, `fullName`, `avatar` (file), `coverImage` (file, optional)
* `POST /api/v1/users/login` - Log in a user.
    * **Body (json):** `email` or `username`, `password`
* `POST /api/v1/users/logout` - Log out the currently authenticated user.
    * **Authorization:** Bearer Token (access token required)
* `POST /api/v1/users/refresh-token` - Request a new access token using a refresh token.

### Channel Routes

* `GET /api/v1/users/c/:username` - Get the public profile of a user's channel.
    * **Authorization:** Bearer Token (optional, to check subscription status)
