# API Endpoint Template

## Purpose
Generate RESTful API endpoints with proper request/response handling, validation, and error handling.

## Template

```
I need you to create an API endpoint with the following specifications:

**Framework**: [framework_name]
**HTTP Method**: [GET/POST/PUT/DELETE/PATCH]
**Endpoint Path**: [/api/path]
**Purpose**: [clear description of what the endpoint does]

**Request**:
- **Headers**: 
  - [header1]: [description]
  - [header2]: [description]
- **Path Parameters**: 
  - [param1]: [type] - [description]
- **Query Parameters**: 
  - [param1]: [type] - [description] (optional/required)
- **Body** (if applicable):
  ```json
  {
    "field1": "type - description",
    "field2": "type - description"
  }
  ```

**Response**:
- **Success (200/201)**: 
  ```json
  {
    "field1": "type - description",
    "field2": "type - description"
  }
  ```
- **Error Responses**:
  - 400: [description]
  - 401: [description]
  - 404: [description]
  - 500: [description]

**Requirements**:
- Validate all inputs
- Implement proper error handling
- Add authentication/authorization if needed
- Include logging
- Follow RESTful conventions
- Add appropriate status codes

**Business Logic**:
- [logic step 1]
- [logic step 2]
```

## Example

```
I need you to create an API endpoint with the following specifications:

**Framework**: Express.js (Node.js)
**HTTP Method**: POST
**Endpoint Path**: /api/users
**Purpose**: Create a new user account

**Request**:
- **Headers**: 
  - Content-Type: application/json
  - Authorization: Bearer token (optional for admin features)
- **Body**:
  ```json
  {
    "username": "string - unique username (3-20 chars)",
    "email": "string - valid email address",
    "password": "string - password (min 8 chars)",
    "firstName": "string - user's first name",
    "lastName": "string - user's last name"
  }
  ```

**Response**:
- **Success (201)**: 
  ```json
  {
    "id": "string - generated user ID",
    "username": "string - username",
    "email": "string - email",
    "firstName": "string - first name",
    "lastName": "string - last name",
    "createdAt": "string - ISO timestamp"
  }
  ```
- **Error Responses**:
  - 400: Invalid input data or validation failure
  - 409: Username or email already exists
  - 500: Internal server error

**Requirements**:
- Validate all inputs (email format, password strength, username uniqueness)
- Hash password before storing
- Implement proper error handling with descriptive messages
- Add request logging
- Follow RESTful conventions
- Return 201 status on successful creation
- Never return password in response

**Business Logic**:
- Check if username or email already exists
- Validate email format
- Validate password strength (min 8 chars, at least 1 number, 1 uppercase)
- Hash password using bcrypt
- Save user to database
- Return sanitized user object
```

## Tips

1. **Specify the framework** to get framework-specific code
2. **Define clear request/response schemas** with data types
3. **List all possible status codes** and their meanings
4. **Include validation requirements** explicitly
5. **Mention security concerns** like authentication, authorization, input sanitization
6. **Document error scenarios** comprehensively
7. **Specify business logic** step by step
