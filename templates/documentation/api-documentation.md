# API Documentation Template

## Purpose
Generate comprehensive API documentation with examples, request/response formats, and error handling.

## Template

```
I need you to create API documentation for the following endpoint:

**Endpoint**: [HTTP_METHOD] [/api/path]
**Description**: [clear description of what the endpoint does]

**Authentication**: [Required/Not Required - type of auth]

**Request Details**:
- **Headers**:
  - [header_name]: [description]
- **Path Parameters**:
  - [param_name]: [type] - [description]
- **Query Parameters**:
  - [param_name]: [type] - [description] (optional/required)
- **Request Body** (if applicable):
  ```json
  [example request body]
  ```

**Response Details**:
- **Success Response (2xx)**:
  - Status Code: [code]
  - Body:
    ```json
    [example success response]
    ```
- **Error Responses**:
  - [4xx/5xx]: [description]
    ```json
    [example error response]
    ```

**Code Examples**:
- [Language 1]
- [Language 2]
- [Language 3]

**Rate Limiting**: [if applicable]
**Notes**: [any additional information]

Please format this as professional API documentation with clear sections and examples.
```

## Example

```
I need you to create API documentation for the following endpoint:

**Endpoint**: GET /api/users/{userId}/orders
**Description**: Retrieve all orders for a specific user with optional filtering

**Authentication**: Required - Bearer token in Authorization header

**Request Details**:
- **Headers**:
  - Authorization: Bearer {token}
  - Content-Type: application/json
- **Path Parameters**:
  - userId: string - The unique identifier of the user
- **Query Parameters**:
  - status: string - Filter by order status (pending, completed, cancelled) (optional)
  - limit: integer - Maximum number of results (default: 20, max: 100) (optional)
  - offset: integer - Number of results to skip for pagination (default: 0) (optional)

**Response Details**:
- **Success Response (200)**:
  - Status Code: 200 OK
  - Body:
    ```json
    {
      "orders": [
        {
          "orderId": "ord_123abc",
          "userId": "usr_456def",
          "status": "completed",
          "items": [...],
          "total": 99.99,
          "createdAt": "2024-01-15T10:30:00Z"
        }
      ],
      "pagination": {
        "total": 45,
        "limit": 20,
        "offset": 0
      }
    }
    ```
- **Error Responses**:
  - 401 Unauthorized: Missing or invalid authentication token
    ```json
    {
      "error": "Unauthorized",
      "message": "Invalid or expired token"
    }
    ```
  - 404 Not Found: User not found
    ```json
    {
      "error": "Not Found",
      "message": "User with ID usr_456def not found"
    }
    ```

**Code Examples**:
Include examples in JavaScript (fetch), Python (requests), and cURL

**Rate Limiting**: 100 requests per minute per user
**Notes**: Orders are returned in descending order by creation date
```

## Tips

1. **Include authentication details** clearly
2. **Provide realistic examples** with actual data structures
3. **Document all possible responses** including errors
4. **Add code examples** in multiple popular languages
5. **Specify rate limits** and pagination details
6. **Include edge cases** and special behaviors
