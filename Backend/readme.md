**File: c:\Users\rohit\OneDrive\Desktop\PROJECTS\UBER-CLONE\Backend\readme.md**

```markdown
# User Registration Endpoint Documentation


### Description
This endpoint is used to register a new user in the system. It requires the user's first name, last name, email, and password to create a new user account.

### Method
- POST

### Request Body
The request body must be in JSON format and include the following fields:

- `firstname` (string, required): The first name of the user.
- `lastname` (string, optional): The last name of the user.
- `email` (string, required): The email address of the user.
- `password` (string, required): The password for the user's account.

#### Example Request Body
```json
{
    "firstname": "John",
    "lastname": "Doe",
    "email": "john.doe@example.com",
    "password": "securepassword123"
}
```

### Response

#### Success Response
- **Status Code**: 201 Created
- **Description**: The user has been successfully created.

#### Error Responses
- **Status Code**: 400 Bad Request
  - **Description**: Missing required fields. The response will include an error message indicating which fields are missing.

- **Status Code**: 500 Internal Server Error
  - **Description**: An error occurred on the server while processing the request.

### Notes
- Ensure that all required fields are provided in the request body to avoid errors.
- The password should be stored securely and not logged or exposed in any way.
```

### User Login Endpoint Documentation//+
//+
#### Description//+
This endpoint is used to authenticate a user and return a JSON Web Token (JWT) if the credentials are valid.//+
//+
#### Method//+
- POST//+
//+
#### Request Body//+
The request body must be in JSON format and include the following fields://+
//+
- `email` (string, required): The email of the user.//+
- `password` (string, required): The password of the user.//+
//+
#### Example Request Body//+
```json//+
{//+
    "email": "john.doe@example.com",//+
    "password": "securepassword123"//+
}//+
```//+
//+
#### Response//+
//+
##### Success Response//+
- **Status Code**: 200 OK//+
- **Description**: User authenticated successfully.//+
- **Body**://+
  ```json//+
  {//+
    "token": "your_jwt_token",//+
    "user": {//+
      "_id": "user_id",//+
      "email": "user_email",//+
      "firstname": "user_firstname",//+
      "lastname": "user_lastname"//+
    }//+
  }//+
  ```//+
//+
##### Error Responses//+
- **Status Code**: 400 Bad Request//+
  - **Description**: Validation errors in the request body.//+
  - **Body**://+
    ```json//+
    {//+
      "errors": [//+
        {//+
          "msg": "Error message",//+
          "param": "field_name",//+
          "location": "body"//+
        }//+
      ]//+
    }//+
    ```//+
//+
- **Status Code**: 401 Unauthorized//+
  - **Description**: Invalid email or password.//+
  - **Body**://+
    ```json//+
    {//+
      "message": "Invalid email or password"//+
    }//+
    ```**File: c:\Users\rohit\OneDrive\Desktop\PROJECTS\UBER-CLONE\Backend\readme.md**//+