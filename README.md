Certainly! I'll create comprehensive documentation for your UBER-CLONE project based on the information we have so far. This will include the authentication middleware and the user management endpoints we've discussed.

**File: c:\Users\rohit\OneDrive\Desktop\PROJECTS\UBER-CLONE\README.md**

```markdown
# UBER-CLONE Backend API

This is the backend API for the UBER-CLONE project. It provides user authentication and management functionalities.

## Table of Contents

1. [Authentication](#authentication)
2. [User Management Endpoints](#user-management-endpoints)
   - [Get User Profile](#get-user-profile)
   - [User Logout](#user-logout)

## Authentication

The API uses JWT (JSON Web Tokens) for authentication. Protected routes require a valid JWT token in the Authorization header.

### Authentication Middleware

The `authUser` middleware is used to authenticate requests to protected routes. It checks for a valid JWT token in the request cookies or Authorization header.

- If no token is provided, it returns a 401 Unauthorized response.
- It checks if the token is blacklisted (for logged out users).
- It verifies the token using the JWT_SECRET environment variable.
- If the token is valid, it attaches the user object to the request for use in subsequent middleware or route handlers.

## User Management Endpoints

### Get User Profile

Retrieves the profile information of the authenticated user.

- **URL:** `/users/profile`
- **Method:** `GET`
- **Auth required:** Yes
- **Headers:**
  - `Authorization: Bearer <token>`

#### Success Response

- **Code:** 200 OK
- **Content example:**

```json
{
  "user": {
    "_id": "60d3b41f0f72a1234567890a",
    "name": "John Doe",
    "email": "johndoe@example.com",
    "phoneNumber": "+1234567890"
  }
}
```

#### Error Response

- **Code:** 401 Unauthorized
- **Content:**

```json
{
  "message": "Unauthorized"
}
```

### User Logout

Logs out the currently authenticated user by invalidating their token.

- **URL:** `/users/logout`
- **Method:** `POST`
- **Auth required:** Yes
- **Headers:**
  - `Authorization: Bearer <token>`

#### Success Response

- **Code:** 200 OK
- **Content example:**

```json
{
  "message": "Logged out successfully"
}
```

#### Error Response

- **Code:** 401 Unauthorized
- **Content:**

```json
{
  "message": "Unauthorized"
}
```

- **Code:** 500 Internal Server Error
- **Content:**

```json
{
  "message": "An error occurred while logging out"
}
```

## Environment Variables

The following environment variables are required:

- `JWT_SECRET`: Secret key used for signing and verifying JWT tokens

## Dependencies

- bcrypt: For password hashing
- jsonwebtoken: For generating and verifying JWT tokens
- express: Web application framework
- mongoose: MongoDB object modeling tool

## Getting Started

1. Clone the repository
2. Install dependencies: `npm install`
3. Set up environment variables
4. Start the server: `npm start`

## Contributing

Please read CONTRIBUTING.md for details on our code of conduct, and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
```

This README provides a comprehensive overview of your project, including authentication details, API endpoints, environment variables, and getting started instructions. You can further customize this README by adding more sections such as:

1. Project structure
2. Database schema
3. Testing instructions
4. Deployment guidelines

Remember to keep this documentation up-to-date as you add more features to your UBER-CLONE project.