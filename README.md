## DanaKu API Documentation

DanaKu is a RESTful API for managing users. This collection provides endpoints to create, retrieve, update, and delete user records, along with a simple health-check endpoint.

### 📂 Project Folder Structure
```sql
src
├── main
│   ├── java
│   │   └── ezdev
│   │       └── danaku
│   │           ├── DanaKuApiApplication.java
│   │           ├── controller
│   │           │   ├── HelloController.java
│   │           │   └── user
│   │           │       └── UserController.java
│   │           ├── models
│   │           │   └── user
│   │           │       └── User.java
│   │           └── repository
│   │               └── UserRepository.java
│   └── resources
│       ├── application.properties
│       ├── static
│       └── templates
└── test
    └── java
        └── ezdev
            └── danaku
                └── DanaKuApiApplicationTests.java

```

### 🚀 Base URL

```
http://localhost:8080/api
```

### 🔐 Authentication

No authentication configured yet — all endpoints are public.

---

### 🗂️ API Overview

| Group | Endpoint          | HTTP Method | Description                  |
| ----- | ----------------- | ----------- | ---------------------------- |
| Hello | `/hello`          | GET         | Simple health check endpoint |
| Users | `/users`          | POST        | Create new user              |
| Users | `/users/all`      | GET         | Retrieve all users           |
| Users | `/users/{userId}` | PUT         | Update user by UUID          |
| Users | `/users/{userId}` | DELETE      | Delete user by UUID          |

---

## 🧩 Endpoint Details

### Hello

| Method | Path | Purpose |
| --- | --- | --- |
| `GET` | `/hello` | Health check endpoint to verify the API is running |

**Sample Response:**

``` json
"Hello, World!"
 ```

---

### Users Folder

All user-related endpoints are grouped in the **Users** folder.

#### Create User

| Method | Path | Purpose |
| --- | --- | --- |
| `POST` | `/users` | Create a new user record |

**Sample Request Body:**

``` json
{
  "name": "John Doe",
  "email": "john@example.com"
}

 ```

**Sample Response:**

``` json
{
  "id": "uuid-string",
  "name": "John Doe",
  "email": "john@example.com"
}

 ```

#### Get All Users

| Method | Path | Purpose |
| --- | --- | --- |
| `GET` | `/users/all` | Retrieve a list of all users |

**Sample Response:**

``` json
[
  {
    "id": "uuid-string",
    "name": "John Doe",
    "email": "john@example.com"
  }
]

 ```

#### Update User

| Method | Path | Purpose |
| --- | --- | --- |
| `PUT` | `/users/{userId}` | Update an existing user by their UUID |

**Sample Request Body:**

``` json
{
  "name": "Jane Doe",
  "email": "jane@example.com"
}

 ```

**Sample Response:**

``` json
{
  "id": "uuid-string",
  "name": "Jane Doe",
  "email": "jane@example.com"
}

 ```

#### Delete User By Id

| Method | Path | Purpose |
| --- | --- | --- |
| `DELETE` | `/users/{userId}` | Delete a user by their UUID |

**Sample Response:**

```
204 No Content

 ```

---

## ⚙️ Getting Started
1. Ensure your local server is running on `http://localhost:8080`
2. Use the **Hello** request to verify connectivity
3. Use the **Users** folder endpoints to manage user records
4. Replace `{userId}` path parameters with actual UUIDs when updating or deleting users