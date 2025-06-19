# Mini Project: Express.js REST API

## Student Name:
(Your Name Here)

## Objective
The goal of this assessment is to evaluate your ability to create a simple REST API using Express.js. You will demonstrate an understanding of Node.js, Express.js, and RESTful API principles.

---

## 1. Setting Up the API

### ✔ Express Application
The project uses a basic Express.js setup with middleware to parse JSON data:
```javascript
const express = require('express');
const app = express();
app.use(express.json());
```

### ✔ Root Route
The root route returns a "Hello, World!" message:
```javascript
app.get('/', (req, res) => {
  res.send('Hello, World!');
});
```

### ✔ Middleware and Error Handling
- `express.json()` is used to parse request bodies.
- Custom error handling middleware is implemented to catch 404 and 500 errors.

---

## 2. Creating Routes (CRUD Operations)

The following RESTful endpoints are implemented:

| Method | Endpoint       | Description                     |
|--------|----------------|---------------------------------|
| GET    | `/items`       | Retrieve all items              |
| GET    | `/items/:id`   | Retrieve an item by ID          |
| POST   | `/items`       | Create a new item               |
| PUT    | `/items/:id`   | Update an item by ID            |
| DELETE | `/items/:id`   | Delete an item by ID            |

---

## 3. Data Management

- Data is stored in an in-memory array.
- Each item has the following structure:
```json
{
  "id": 1,
  "name": "Item Name",
  "description": "Item Description"
}
```
- Data is validated before creation and update:
  - `name` and `description` are required fields.

---

## 4. Error Handling

### ✔ 400 Bad Request
Returned when required fields are missing:
```json
{ "error": "Name and description are required" }
```

### ✔ 404 Not Found
Returned when an item is not found:
```json
{ "error": "Item not found" }
```

### ✔ 500 Internal Server Error
Returned for unhandled exceptions:
```json
{ "error": "Internal Server Error" }
```

---

## 5. Testing

Here are example requests using tools like Postman:

### ✔ Create a New Item
**POST** `/items`  
```json
{
  "name": "Notebook",
  "description": "A simple notebook"
}
```
**Response:**
```json
{
  "id": 3,
  "name": "Notebook",
  "description": "A simple notebook"
}
```

### ✔ Retrieve All Items
**GET** `/items`  
**Response:**
```json
[
  { "id": 1, "name": "Item One", "description": "First item" },
  { "id": 2, "name": "Item Two", "description": "Second item" },
  ...
]
```

### ✔ Delete an Item
**DELETE** `/items/1`  
**Response:**
```json
{ "message": "Item deleted successfully" }
```

---

## 6. Submission Requirements

✅ Working Express.js application with all specified routes  
✅ `README.md` with setup instructions and API documentation  
✅ Sample requests and expected responses provided above  

---

## 7. How to Run the Project

1. Install dependencies:
```bash
npm install express
```

2. Start the server:
```bash
node index.js
```

3. Use Postman or browser to test routes on `http://localhost:3000`

---

## 8. Folder Structure

```
mini-project-api/
├── index.js
└── README.md
```

---

## 9. Final Notes

This project is a minimal Express.js REST API that satisfies all assessment criteria using clear structure, validation, and error handling. The project does not use a database for simplicity, but can be extended using MongoDB or PostgreSQL.

