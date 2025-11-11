# **Backend Notes – Section 1.2 (Complete & Exam-Ready)**

## **1. Definition of Frontend and Backend**

### **Frontend (Client)**

- Runs on the user’s device (browser/mobile app).
- Responsible for UI rendering, collecting user input, and sending structured requests to the backend.
- Typically built using HTML, CSS, JavaScript, or frameworks like React, Angular, Vue.

### **Backend (Server)**

- Runs on a remote server.
- Responsible for:
    - Processing requests
    - Executing business logic
    - Interacting with the database
    - Verifying authentication and authorization
    - Sending structured responses back to the client
- Built using languages and frameworks like:
    - Node.js/Express
    - Python/Django
    - Java/Spring
    - Go/Fiber, etc.

---

## **2. Client vs Server: Clear Technical Distinction**

### **Client**

- Presentational layer.
- Requests data from the backend.
- Updates UI based on response data.

### **Server**

- Core logic layer.
- Responsible for computation, decisions, and data operations.
- Considered the “single source of truth” because the database and validated logic live here.

---

## **3. The Request-Response Cycle (Technical Breakdown)**

This is the fundamental sequence followed by every interaction between client and server.

![[Pasted image 20251111134757.png]]
### **Step-by-step Breakdown**

1. **Client initiates an HTTP request**
    - Includes:
        - HTTP Method (GET, POST, PUT, DELETE)
        - URL/Endpoint (e.g., /api/v1/users/profile)
        - Headers (Authorization: Bearer `<token>`, Content-Type)
        - Optional body (for POST/PUT requests containing data)
2. **Request travels to the server**
    - Goes through network layers (TCP/IP, DNS resolution, routing).
3. **Server receives the request**
    - The web server (e.g., Express.js app) parses:
        - Method
        - URL
        - Headers
    - Routes it to the correct controller or handler function.
4. **Backend processes the request**  
    This may involve multiple operations:
    - **Authentication**: Verifies user identity (e.g., decode JWT).
    - **Authorization**: Checks if the user has permission to access resource.
    - **Database operations**: CRUD interactions using ORM/ODM (Mongoose).
    - **Business logic execution**: Rules, validations, data transformations.
5. **Server constructs an HTTP response**
    - Includes:
        - Status Code (200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 500 Internal Server Error)
        - Headers (Content-Type: application/json)
        - Body (usually JSON: { key: value })
6. **Response travels back to the client**
7. **Client processes the response**
    - JavaScript code parses response JSON.
    - UI updates accordingly.

---

## **4. Core Responsibilities of Backend Systems**

### **A. Business Logic**

Rules that define how the system behaves. Examples:

- Calculating totals
- Validating inputs
- Applying conditional rules
- Formatting or transforming data
- Defining what happens when a specific endpoint is hit

This logic is central to the functionality and correctness of an application.

---

### **B. Database Interaction**

Backend handles all communication with the database.

**CRUD:**

- **Create**: Insert new data
- **Read**: Retrieve existing data
- **Update**: Modify existing data
- **Delete**: Remove data

In modern web apps, this is executed using:

- SQL databases: PostgreSQL, MySQL
- NoSQL: MongoDB (with Mongoose ODM)

Backend ensures:

- Data integrity
- Proper schema usage
- Query optimization
- Error handling

---

### **C. Authentication & Authorization**

#### **Authentication**

Determines _who_ the user is.  
Common methods:

- Username + password with hashing (bcrypt)
- Token-based authentication (JWT)
- OAuth (Google, GitHub)

#### **Authorization**

Determines _what_ an authenticated user is allowed to do.  
Examples:

- Prevent user A from editing user B’s posts
- Admin-only routes
- Restrictions on sensitive data

Authorization logic typically runs after authentication.

---

### **D. API Layer**

The API defines:

- Endpoints (URLs)
- Allowed HTTP methods
- Required request structure (body, params, headers)
- Response format and status codes

API is a contract between client and server.  
Frontend must follow the API specification for communication to work correctly.

---

## **5. Technical Mapping of a Backend System**

### **Components**

1. **Client**  
    Sends HTTP requests.
2. **HTTP Transport Layer**  
    Carries the request over the network.
3. **Server Application (Node.js/Express)**  
    Interprets request and runs logic.
4. **Business Logic Layer**  
    Core engine of functionality.
5. **Database Layer**  
    Permanent storage using MongoDB or similar.
6. **Response Generator**  
    Forms the final HTTP response with status code + JSON body.

---

## **6. Practical Activity Breakdown (Exam-Safe Version)**

The classroom activity maps directly to backend architecture:

|Activity Role|Technical Equivalent|
|---|---|
|Customer|Client (Frontend UI)|
|Waiter|HTTP layer transporting request/response|
|Head Chef|Backend server logic|
|Pantry Chef|Database operations|
|Written order|HTTP Request|
|Completed dish|HTTP Response|

This activity demonstrates:

- Request formation
- Transport
- Backend handling
- Database lookup
- Response generation

---

## **7. Key Terms (Precise Definitions)**

**Client:** The device/browser/app sending requests to a server.  
**Server:** The machine running backend logic and responding to requests.  
**Request:** Structured message sent from client to server.  
**Response:** Structured message sent from server to client.  
**API:** Set of rules defining how client and server communicate (routes, methods, formats).  
**Business Logic:** Functional rules that govern how the system behaves.  
**CRUD:** Create, Read, Update, Delete operations in a database.  
**Authentication:** Verifying a user’s identity.  
**Authorization:** Verifying a user’s access rights.  
**Database:** Storage system for persistent data.  
**Endpoint:** URL that identifies a specific backend resource/action.  
**HTTP Method:** Defines the action to be performed (GET, POST, PUT, DELETE).  
**Status Code:** Numeric indicator of request outcome (200, 404, 500, etc.).

---

## **8. Summary (Exam-Optimized)**

- Frontend handles UI; backend handles processing, logic, and data.
- Backend acts as the single source of truth using database + logic.
- Every interaction follows the request-response cycle.
- Backend responsibilities include business logic, database interaction, authentication, authorization, and API management.
- Understanding how each component interacts is foundational for backend engineering.