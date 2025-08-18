# Chai and Backend

This is a video series on backend with javascript.

## Project Description

This project is a backend for a video platform, likely called "videotube". It includes user authentication, video management, and subscription features. The project is built with Node.js and Express, and uses MongoDB as its database.

## Features

* **User Authentication:**
    * User registration and login
    * JWT-based authentication
    * Password encryption using bcrypt
    * Access and refresh token generation
    * Logout functionality
* **User Profile:**
    * Get current user details
    * Update account details
    * Update user avatar and cover image
    * Get user channel profile
* **Video Management:**
    * Video model with details like video file, thumbnail, title, description, duration, views, and owner
* **Subscription:**
    * Subscription model to manage user subscriptions to channels

## Getting Started

### Prerequisites

* Node.js
* npm
* MongoDB

### Installation

1.  Clone the repository:
    ```bash
    git clone <repository-url>
    ```
2.  Install NPM packages:
    ```bash
    npm install
    ```
3.  Create a `.env` file in the root directory and add the following environment variables:
    ```
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

## Dependencies

* [bcrypt](https://www.npmjs.com/package/bcrypt): Library to help you hash passwords.
* [cloudinary](https://www.npmjs.com/package/cloudinary): Cloudinary SDK for Node.js.
* [cookie-parser](https://www.npmjs.com/package/cookie-parser): Parse Cookie header and populate `req.cookies` with an object keyed by the cookie names.
* [cors](https://www.npmjs.com/package/cors): Node.js CORS middleware.
* [dotenv](https://www.npmjs.com/package/dotenv): Dotenv is a zero-dependency module that loads environment variables from a `.env` file into `process.env`.
* [express](https://www.npmjs.com/package/express): Fast, unopinionated, minimalist web framework for Node.js.
* [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken): An implementation of JSON Web Tokens.
* [mongoose](https://www.npmjs.com/package/mongoose): Mongoose is a MongoDB object modeling tool designed to work in an asynchronous environment.
* [mongoose-aggregate-paginate-v2](https://www.npmjs.com/package/mongoose-aggregate-paginate-v2): A mongoose plugin to paginate aggregate queries.
* [multer](https://www.npmjs.com/package/multer): Multer is a node.js middleware for handling `multipart/form-data`.

## Dev Dependencies

* [nodemon](https://www.npmjs.com/package/nodemon): Nodemon is a tool that helps develop node.js based applications by automatically restarting the node application when file changes in the directory are detected.
* [prettier](https://www.npmjs.com/package/prettier): Prettier is an opinionated code formatter.
