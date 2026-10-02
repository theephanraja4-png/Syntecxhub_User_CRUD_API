# Syntecxhub User CRUD REST API

A backend REST API for managing users using **Node.js, Express.js, MongoDB Atlas, and Mongoose**.

This project was developed as part of the **Syntecxhub Backend Development Internship – Week 1, Task 1**.

The API implements complete CRUD operations with input validation, error handling, duplicate email detection, and MongoDB persistence.

## 🚀 Features

- ✅ Create a new user
- ✅ Get all users
- ✅ Get a user by ID
- ✅ Update an existing user
- ✅ Delete a user
- ✅ User input validation
- ✅ Email validation
- ✅ Duplicate email detection
- ✅ Invalid MongoDB ObjectId handling
- ✅ Non-existing user handling
- ✅ API health check
- ✅ Appropriate HTTP status codes
- ✅ Centralized error handling
- ✅ MongoDB Atlas integration
- ✅ Postman API testing

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | REST API framework |
| MongoDB Atlas | Cloud database |
| Mongoose | MongoDB ODM |
| Postman | API testing |
| JavaScript | Backend programming language |

## 📁 Project Structure

    Syntecxhub_User_CRUD_API/
    ├── .resources/
    │   ├── 1. Health Check.request.yaml
    │   ├── 2. Create User.request.yaml
    │   ├── 3. Get All Users.request.yaml
    │   ├── 4. Get User by ID.request.yaml
    │   ├── 5. Update User.request.yaml
    │   ├── 6. Delete User.request.yaml
    │   ├── 7. Validation Failure (Missing Email).request.yaml
    │   ├── 8. Duplicate Email Test.request.yaml
    │   ├── 9. Invalid ObjectId Format.request.yaml
    │   └── 10. Non-Existing User ID.request.yaml
    │
    ├── src/
    │   ├── config/
    │   ├── controllers/
    │   ├── middleware/
    │   ├── models/
    │   ├── routes/
    │   ├── app.js
    │   └── server.js
    │
    ├── .env.example
    ├── .gitignore
    ├── package.json
    ├── package-lock.json
    └── README.md

## 🔗 API Endpoints

**Base URL:** `http://localhost:5000`

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/health` | Check API status |
| POST | `/api/users` | Create a new user |
| GET | `/api/users` | Get all users |
| GET | `/api/users/:id` | Get a user by ID |
| PUT | `/api/users/:id` | Update a user |
| DELETE | `/api/users/:id` | Delete a user |

## 👤 User Data

A user contains information such as:

    {
      "name": "Sarah Connor",
      "email": "sarah@example.com",
      "age": 25
    }

The API also maintains creation and update timestamps for stored users.

## 📝 Create User

**Method:** `POST`

**Endpoint:** `/api/users`

**Request Body:**

    {
      "name": "Sarah Connor",
      "email": "sarah@example.com",
      "age": 25
    }

**Expected Status:** `201 Created`

**Purpose:** Creates a new user and stores the user in MongoDB.

## 📋 Get All Users

**Method:** `GET`

**Endpoint:** `/api/users`

**Expected Status:** `200 OK`

Returns the users stored in MongoDB.

Example response structure:

    {
      "success": true,
      "count": 1,
      "data": [
        {
          "_id": "USER_ID",
          "name": "Sarah Connor",
          "email": "sarah@example.com",
          "age": 25
        }
      ]
    }

## 🔍 Get User by ID

**Method:** `GET`

**Endpoint:** `/api/users/:id`

**Example:** `/api/users/USER_ID`

**Expected Status:** `200 OK`

If the user does not exist, the API returns `404 Not Found`.

Invalid MongoDB ObjectId formats are also handled.

## ✏️ Update User

**Method:** `PUT`

**Endpoint:** `/api/users/:id`

**Example Request Body:**

    {
      "name": "Jane Updated",
      "age": 23
    }

**Expected Status:** `200 OK`

The API updates the requested user and returns the updated data.

## 🗑️ Delete User

**Method:** `DELETE`

**Endpoint:** `/api/users/:id`

**Expected Status:** `200 OK`

Example successful response:

    {
      "success": true,
      "message": "User deleted successfully"
    }

## ❤️ Health Check

**Method:** `GET`

**Endpoint:** `/api/health`

**Expected Status:** `200 OK`

Example response:

    {
      "success": true,
      "message": "API is running"
    }

## ⚠️ Validation & Error Handling

The API handles different invalid request scenarios.

### Missing Email

Example request:

    {
      "name": "Missing Email",
      "age": 25
    }

The API rejects the request because email is required.

### Duplicate Email

Attempting to create another user with an existing email address returns an appropriate conflict response.

### Invalid User ID

Invalid MongoDB ObjectId formats are handled without crashing the server.

### Non-Existing User

Requests for users that do not exist return an appropriate `404 Not Found` response.

## 🗄️ MongoDB Atlas

The application uses **MongoDB Atlas** as the cloud database and **Mongoose** for database interaction.

The MongoDB connection is configured through an environment variable.

### Environment Variables

Create a `.env` file in the project root.

    MONGODB_URI=your_mongodb_atlas_connection_string
    PORT=5000

For security, the actual `.env` file is excluded from Git using `.gitignore`.

**Never commit your MongoDB credentials or connection string to GitHub.**

## ⚙️ Installation

Clone the repository:

    git clone https://github.com/theephanraja4-png/Syntecxhub_User_CRUD_API.git

Navigate into the project:

    cd Syntecxhub_User_CRUD_API

Install dependencies:

    npm install

Create a `.env` file and configure your MongoDB Atlas connection:

    MONGODB_URI=your_mongodb_atlas_connection_string
    PORT=5000

## ▶️ Run the Application

Start the development server:

    npm run dev

The API will be available at:

`http://localhost:5000`

Health check:

`http://localhost:5000/api/health`

## 🧪 API Testing

The API was tested using **Postman**.

The following scenarios were tested:

1. Health Check
2. Create User
3. Get All Users
4. Get User by ID
5. Update User
6. Delete User
7. Validation Failure — Missing Email
8. Duplicate Email
9. Invalid ObjectId Format
10. Non-Existing User ID

These tests cover both successful API operations and common failure scenarios.

## 📚 Learning Outcomes

Through this project, I gained practical experience with:

- REST API development
- Express.js routing
- Node.js backend development
- MongoDB database integration
- Mongoose models and queries
- CRUD operations
- Input validation
- HTTP status codes
- Error handling
- Environment variable management
- Postman API testing
- Git and GitHub workflow

## 🎓 Internship

**Organization:** Syntecxhub

**Internship:** Backend Development Internship

**Task:** Week 1 – Task 1

**Project:** User CRUD REST API

## 👨‍💻 Author

**Theepan Raja S**

GitHub: `https://github.com/theephanraja4-png`

## 📌 Project Status

**Week 1 – Task 1: Completed ✅**

The User CRUD REST API has been implemented, connected to MongoDB Atlas, tested using Postman, and pushed to GitHub.
