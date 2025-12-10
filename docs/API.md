# API Documentation

## Users API

### GET /api/users
Get list of all users.

**Response:**
```json
[
  {
    "id": "123",
    "name": "John Doe",
    "email": "john@example.com"
  }
]
```

### GET /api/users/:id
Get a specific user by ID.

**Parameters:**
- `id` (string) - User ID

**Response:**
```json
{
  "id": "123",
  "name": "John Doe",
  "email": "john@example.com"
}
```

### GET /api/users/:name  
Added in v1.0.1

Get a specific user by name.

**Parameters:**
- `name` (string) - User name

**Response:**
```json
{
  "id": "123",
  "name": "John Doe",
  "email": "john@example.com"
}
```

Note: When both `:id` and `:name` routes exist under `/api/users`, your router's matching order determines which route is used. In production, prefer a distinct path such as `/api/users/by-name/:name` to avoid ambiguity.

### POST /api/users  
Added in v1.0.1

Create a new user.

**Request Body (application/json):**
```json
{
  "name": "John Doe",
  "email": "john@example.com"
}
```

**Response:**
```json
{
  "id": "123",
  "name": "John Doe",
  "email": "john@example.com"
}
```

### DELETE /api/users/:id  
Added in v1.0.1

Delete a user by ID.

**Parameters:**
- `id` (string) - User ID

**Response:**
```json
true
```

## Authentication

All endpoints require Bearer token authentication.

**Header:**
```
Authorization: Bearer <token>
```
