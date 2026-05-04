## 📚 Book API ➖ Comprehensive API Test Suite<br>
A full-cycle API testing project using Postman to validate the Simple Books API, covering API status checks, book retrieval, filtering, authentication, and order management<br>
through structured GET and POST requests.<br>

🔐 Access tokens and authentication credentials have been omitted from all documentation for security purposes.<br>

<hr>
###📋 Project Overview
This project validates the functionality, reliability, and error handling of the Simple Books API through a structured series of Postman requests. Testing covered both positive scenarios (verifying expected behavior) and negative scenarios (validating proper error responses for unauthorized or invalid requests).
The Postman Collection is included in this repository and can be imported directly to replicate all test cases.
﻿<hr>

### 🛠 Tools & Technologies
| Tool |  Purpose |
| --- | --- |
| [ Postman](https://postman.com)  | API client for building, executing, and documenting requests |
| Simple Books API | Third-party REST API for managing book and order data |
| JSON | Response format validated across all test cases |

<hr>

### 📡 API Endpoints Tested
Base URL
[https://simple-books-api.glitch.me](https://simple-books-api.glitch.me)

<hr>

### 📌 Endpoint Summary
| Method |  Endpoint | Purpose |
| --- | --- |--- |
|GET | /status | Check API availability |
|GET  |/books  |Retrieve full list of books|
|GET |/books?type=fiction | Filter books by fiction type |
|GET |/books?type=non-fiction |Filter books by non-fiction type |
|GET |/books/{bookId}| Retrieve a single book by ID |
|POST |/api-clients |Register an API client to obtain access token |
|POST | /orders| Submit a new book order (requires authentication)|
|GET | /orders | Retrieve all orders (requires authentication) |
|PATCH | /orders/{orderId} | Update an existing order |
|DELETE |/orders/{orderId}| Delete an order |

<hr>

###🔐 Authentication
The API requires an access token for order-related endpoints. To obtain a token:

1. Send a POST request to /api-clients with the following JSON body:
```json

{
  "clientName": "Jane Doe",
  "clientEmail": "JaneDoer@email.com"
}
```
2. Copy the accessToken from the response
3. Store it as a Postman environment variable {{ACCESS_TOKEN}}
4. Include it in the Authorization header for all order requests
<hr>

### 🧪 Testing Approach<br>
#### 🔷 Functional Testing (Positive Cases)<br>
📌 Verified that valid requests return correct HTTP status codes, accurate data, and properly structured JSON responses.<br>

#### 🔷 Negative & Edge Case Testing<br>
📌 Submitted unauthorized, malformed, and invalid requests to confirm the API handles failures gracefully with appropriate error responses.<br>

#### 🔷 Response Validation<br>
Each response was checked for:<br>
📌 Correct HTTP status codes (200 OK, 201 Created, 401 Unauthorized, 404 Not Found)<br>
📌 Accurate JSON response structure and required fields<br>
📌 Proper authentication enforcement on protected endpoints<br>

<hr>

### 🔍 Test Scenarios Covered
| Scenario Type | Description| 
| --- | --- |
|✅ GET /status| Returns 200 OK confirming API is running|
|✅ GET /books |Returns full list of available books|
|✅ GET /books?type=fiction |Returns filtered fiction books only|
|✅ GET /books?type=non-fiction |Returns filtered non-fiction books only|
|✅ GET /books/{id} |Returns single book by valid ID|
|✅ POST /api-clients |Returns access token for valid registration|
|✅ POST /orders |Creates order successfully with valid token|
|✅ GET /orders |Returns all orders for authenticated user|
|✅ PATCH /orders/{id} |Updates order details successfully|
|✅ DELETE /orders/{id} |Deletes order and confirms removal|
|❌ POST /orders (no token) |Returns 401 Unauthorized|
|❌ GET /books/{invalid id}  |Returns 404 Not Found|
|❌ POST /api-clients (duplicate email) |Returns 409 Conflict|
<hr>


<h2>📗 GET API Status</h2><br>
<br> 
🔄 Checks the status of the API with 200 OK being the goal<BR>

```JSON
{
  "status": "OK"
}

```
﻿<hr>
<h2>📓 GET API Books</h2><br>
<br>
↪️ Returns the complete list of books<br>

```json
{
"id": 1,
"name": "The Russian",
"type": "fiction",
"available": true
},
{
"id": 3,
"name": "The Vanishing Half",
"type": "fiction",
"available": true
},
{
"id": 4,
"name": "The Midnight Library",
"type": "fiction",
"available": true
},
{
"id": 6,
"name": "Viscount Who Loved Me",
"type": "fiction",
"available": true
},
```

﻿<hr>
<h2> 📐 Query Params</h2>
🎭 types:     non-fiction or fiction
<br>
<h2> 📒 POST Order</h2>
<br>

```JSON
{
  "created": true,
  "orderId": "PF6MflJovlMETBo"
}
```

<br>
↘️ Submit a new order after obtaining authentication
<br>
<h3>Result</h3>
<br>

![image](https://github.com/user-attachments/assets/8e2bfa75-0685-4137-a5d3-14a0b96d89de)
<br>
<hr>

## 📁 Repository Contents
|File / Folder |Description |
| --- | ---|
|Postman Collections/ |Exportable Postman collection containing all API requests<br>
|README.md |Project documentation<br>
<hr>

## ▶️ How to Run This Test Suite

1. Clone or download this repository<br>
2. Open Postman<br>
3. Click Import → select the collection file from the Postman Collections/ folder<br>
4. Create a Postman environment and add a variable named ACCESS_TOKEN<br>
5. Run the POST /api-clients request first to generate your token, then paste it into the environment variable<br>
6. Run individual requests or use Collection Runner to execute the full suite<br>
7. Verify responses match the expected status codes and JSON structure above<br>
<hr>

## 📚 Key Takeaways<br>

🎯 Gained hands-on experience testing a full REST API lifecycle, from status checks and data retrieval through authenticated order management<br>
🎯 Strengthened understanding of token-based authentication and how to handle Bearer tokens securely using Postman environment variables<br>
🎯 Practiced designing test cases that cover both happy path and failure scenarios, reinforcing that negative testing is as critical as positive validation<br>
🎯 Learned the importance of testing all HTTP methods (GET, POST, PATCH, DELETE) to ensure complete CRUD coverage rather than focusing on retrieval alone<br>
🎯 Reinforced best practices around credential security; never exposing access tokens or API keys in public repositories<br>
🎯 Improved ability to read, interpret, and validate JSON response structures against expected API behavior<br>

﻿


