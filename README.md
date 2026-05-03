📚 Book API — Comprehensive API Test Suite
A full-cycle API testing project using Postman to validate the Simple Books API, covering API status checks, book retrieval, filtering, authentication, and order management through structured GET and POST requests.

🔐 Access tokens and authentication credentials have been omitted from all documentation for security purposes.<br>

<hr>
📋 Project Overview
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



<h2>GET API Status</h2><br>
<br>
https://simple-books-api.glitch.me/status
<br>
Checks the status of the API with 200 OK being the goal

﻿<hr>
 
<h2>GET API Books</h2><br>
<br>
https://simple-books-api.glitch.me/books
<br>
Returns the complete list of books

﻿<hr>

<h2>Query Params</h2>
types:     non-fiction or fiction
<br>
<h2>POST Order</h2>
<br>
https://simple-books-api.glitch.me/orders
<br>

<br>
<br>
Submit a new order after obtaining authentication
<br>
<h3>Result</h3>
<br>

![image](https://github.com/user-attachments/assets/8e2bfa75-0685-4137-a5d3-14a0b96d89de)
<br>
<hr>


﻿


