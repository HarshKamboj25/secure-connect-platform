
<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=30&duration=3000&pause=1000&color=00D9FF&center=true&vCenter=true&width=850&lines=SECURE+CONNECT+PLATFORM;Secure+Notes+%7C+Real-Time+Communication;Powered+by+Node.js+%26+Socket.IO" alt="Animated Project Heading" />

<br/>

### 🔐 SECURE CONNECT PLATFORM

**A Secure Backend Communication System**

*Secure Notes API • Real-Time Notifications • Room-Based Chat*

<br/>

<img src="https://img.shields.io/badge/PROJECT-Backend%20Development-0A192F?style=for-the-badge&logo=serverfault&logoColor=00D9FF" />
<img src="https://img.shields.io/badge/STATUS-Running-00C853?style=for-the-badge&logo=statuspal&logoColor=white" />
<img src="https://img.shields.io/badge/API-RESTful-FF6C37?style=for-the-badge&logo=postman&logoColor=white" />

<br/><br/>

<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/Socket.IO-010101?style=flat-square&logo=socketdotio&logoColor=white" />
<img src="https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />

<br/><br/>

**Building secure APIs. Enabling real-time communication.**

</div>

---

## 🌐 01. Project Overview

**Secure Connect Platform** is a backend-focused application that combines secure REST API operations with real-time communication using Socket.IO.

The platform provides authenticated note management, token-based authorization, role-based access control, live note notifications, and room-based messaging.

It demonstrates how backend services can handle protected resources while maintaining real-time communication between connected clients.

---

## ✨ 02. Core Features

<table>
<tr>
<td width="50%">

### 🔐 Authentication
- User registration
- Secure password hashing
- JWT-based authentication
- Protected API routes

</td>
<td width="50%">

### 📝 Note Management
- Create secure notes
- Retrieve user notes
- Update existing notes
- Delete notes by ID

</td>
</tr>
<tr>
<td width="50%">

### ⚡ Real-Time Notifications
- Socket.IO integration
- `note:created` event
- Live event delivery
- Connected client handling

</td>
<td width="50%">

### 💬 Real-Time Chat
- Room-based communication
- `join_room` event
- `chat_message` event
- Message broadcasting

</td>
</tr>
</table>

### 🛡️ Additional Capabilities

- Role-Based Access Control (RBAC)
- MongoDB database integration
- Node.js EventEmitter events
- Environment configuration with dotenv
- API testing through Postman

---

## 🧰 03. Technology Stack

| Technology | Application |
|---|---|
| 🟢 Node.js | Backend JavaScript runtime |
| ⚙️ Express.js | REST API and route handling |
| 🍃 MongoDB | Database and document storage |
| 🔌 Socket.IO | Real-time communication |
| 🔑 JWT | Authentication and authorization |
| 🔒 bcryptjs | Password hashing |
| 📬 Postman | API and Socket.IO testing |
| ⚡ EventEmitter | Server-side event handling |
| 🔧 dotenv | Environment variable management |

---

## 🏗️ 04. API Architecture

<div align="center">

### REST API ENDPOINTS

<kbd>BASE URL: http://localhost:5000</kbd>

</div>

| Method | Endpoint | Description |
|:---:|---|---|
| `POST` | `/api/auth/signup` | Register a new user |
| `POST` | `/api/auth/login` | Authenticate user and generate token |
| `GET` | `/api/protected` | Access protected resource |
| `GET` | `/api/admin` | Access admin-only route |
| `POST` | `/api/notes` | Create a new note |
| `GET` | `/api/notes` | Retrieve notes |
| `GET` | `/api/notes/:id` | Retrieve a specific note |
| `PUT` | `/api/notes/:id` | Update an existing note |
| `DELETE` | `/api/notes/:id` | Delete a note |

### 📨 Sample Note Request

```json
{
  "title": "My Note",
  "content": "Note content goes here."
}
```

### 🔑 Authentication Flow

1. Register using the signup endpoint.
2. Log in using valid credentials.
3. Receive a JWT authentication token.
4. Select **Bearer Token** in Postman.
5. Access protected endpoints using the token.

---

## ⚡ 05. Real-Time Communication

Socket.IO enables real-time communication between connected clients and the backend server.

### Event Architecture

| Event | Purpose | Example |
|---|---|---|
| `note:created` | Notify clients when a note is created | User ID + note title |
| `join_room` | Join a chat room | `general` |
| `chat_message` | Send a message inside a room | Username + message |

### 💬 Chat Message Example

```json
{
  "room": "general",
  "username": "Harsh",
  "message": "Hello! Testing real-time chat."
}
```

### 🔔 Note Notification Example

```json
{
  "userId": "USER_ID",
  "title": "Live Notification Test"
}
```

<div align="center">

**REAL-TIME EVENT FLOW**

`Client` → `Socket.IO Server` → `Event Processing` → `Connected Clients`

</div>

---

## 📸 06. Project Demonstration & Testing

<details open>
<summary><b>📝 A. Notes Management | REST API Testing</b></summary>

### 01. Create a Note

<kbd>POST</kbd> <kbd>201 CREATED</kbd>

Successfully created a new note with its title and content.

<img width="100%" src="https://github.com/user-attachments/assets/a3bd7d3e-d0b7-41ed-90d1-d7674503704e" alt="Create note request and response" />

---

### 02. Update a Note

<kbd>PUT</kbd> <kbd>200 OK</kbd>

Successfully updated the existing note using its unique ID.

<img width="100%" src="https://github.com/user-attachments/assets/907710f6-2653-4d08-93b8-0cdcd4d77606" alt="Update note request and response" />

---

### 03. Delete a Note

<kbd>DELETE</kbd> <kbd>200 OK</kbd>

Successfully deleted the selected note.

<img width="100%" src="https://github.com/user-attachments/assets/ff1f413b-31e5-4fa1-bfb5-bbb12ae30edf" alt="Delete note request and response" />

</details>

<details open>
<summary><b>⚡ B. Real-Time Notifications | Socket.IO</b></summary>

### 04. Note Created Event

<kbd>SOCKET.IO</kbd> <kbd>EVENT RECEIVED</kbd>

Demonstration of the `note:created` event triggered after note creation.

<img width="100%" src="https://github.com/user-attachments/assets/013dfbbd-d612-499c-ad4c-6a5b567fb1b8" alt="Socket.IO note created event" />

</details>

<details open>
<summary><b>💬 C. Room-Based Communication | Live Chat</b></summary>

### 05. Join a Chat Room

<kbd>join_room</kbd> <kbd>CONNECTED</kbd>

Joining the `general` room through Socket.IO.

<img width="100%" src="https://github.com/user-attachments/assets/624d95ae-e8dc-4fb1-9a64-ad581b48c290" alt="Socket.IO room join" />

---

### 06. Send a Chat Message

<kbd>chat_message</kbd> <kbd>EVENT SENT</kbd>

Sending a real-time chat message inside the general room.

<img width="100%" src="https://github.com/user-attachments/assets/c5fa2e92-6c3f-4f55-9c2a-95aaac38fe8f" alt="Socket.IO chat message" />

</details>

<details open>
<summary><b>🖥️ D. Backend Monitoring | Server Logs</b></summary>

### 07. Server-Side Event Logs

Terminal output demonstrating server startup, client connection, note creation, and chat message events.

<img width="100%" src="https://github.com/user-attachments/assets/7c3a2af4-5eaf-44c1-b0ed-d77cb5115bb3" alt="Server logs showing note and chat events" />

</details>

---

## 🚀 07. Getting Started

Follow these steps to run the project locally.

### Prerequisites

- Node.js installed
- npm package manager
- MongoDB local instance or MongoDB Atlas
- Postman for API testing

### Step 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <repository-folder>
```

### Step 2. Install Dependencies

```bash
npm install
```

### Step 3. Configure Environment Variables

Create a `.env` file in the root directory.

Configure the variables required by your application.

Example:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_secure_secret
```

Use the exact environment variable names expected by your source code.

**Important:** Never upload your actual `.env` file, database credentials, or JWT secrets to GitHub.

### Step 4. Start the Server

Use the script defined in your `package.json`.

For example:

```bash
npm run dev
```

Or, if using the start script:

```bash
npm start
```

### Step 5. Test the Application

Open Postman and test the REST API endpoints.

For Socket.IO:

1. Connect to `http://localhost:5000`.
2. Listen for the `note:created` event.
3. Send a `join_room` event.
4. Send a `chat_message` event.
5. Observe the received events and server-side logs.

---

## 🔒 08. Security Considerations

- Passwords are hashed using bcryptjs.
- JWT tokens are used for authenticated requests.
- Protected endpoints require valid authentication.
- Role-based access control restricts admin functionality.
- Environment variables are used for sensitive configuration.
- Note operations are associated with authenticated users.

---

## ✅ 09. Testing & Verification

The following results are demonstrated in the project screenshots:

| Test Case | Expected Result | Observed Result |
|---|---|---|
| User Registration | 201 Created | ✅ 201 Created |
| User Login | 200 OK | ✅ 200 OK |
| Protected Resource | 200 OK | ✅ 200 OK |
| Admin Route with User Role | 403 Forbidden | ✅ 403 Forbidden |
| Create Note | 201 Created | ✅ 201 Created |
| Retrieve Notes | 200 OK | ✅ 200 OK |
| Update Note | 200 OK | ✅ 200 OK |
| Delete Note | 200 OK | ✅ 200 OK |
| Note Notification | Event Received | ✅ Received |
| Room Joining | Event Sent | ✅ Received |
| Chat Messaging | Event Sent | ✅ Received |

---

## 📂 10. Project Structure

```text
secure-connect-platform/
│
├── docs/
│   └── postman-test-plan...
│
├── src/
│   ├── config/
│   │   └── database.js
│   │
│   ├── middleware/
│   │   └── authMiddleware.js
│   │
│   └── routes/
│       ├── authRoutes.js
│       └── notesRoutes.js
│
├── .env
├── .env.example
├── .gitignore
├── package.json
├── package-lock.json
├── README.md
└── server.js
```

---

## 🔮 11. Key Learning Outcomes

Through this project, the following backend development concepts were practised:

- Building RESTful APIs using Express.js.
- Implementing authentication and authorization.
- Managing MongoDB documents.
- Performing CRUD operations.
- Integrating Socket.IO for real-time communication.
- Handling custom socket events and chat rooms.
- Testing APIs and real-time events through Postman.
- Managing server configuration using environment variables.

---

<div align="center">

<img src="https://img.shields.io/badge/SECURE-CONNECT-00D9FF?style=for-the-badge&logo=socketdotio&logoColor=white" />

### ⚡ Secure APIs. Real-Time Experiences. Reliable Communication.

**Built with Node.js, Express.js, MongoDB & Socket.IO.**

<br/>

<sub>Web Development III | Backend Application Project</sub>

<br/><br/>

**Thanks for exploring Secure Connect Platform!** 💙

</div>
