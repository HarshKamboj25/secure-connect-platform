<div align="center">

# 🔐 Secure Connect Platform

### Secure Notes API • Real-Time Notifications • Room-Based Chat

A backend-focused application demonstrating authenticated note management and real-time communication with **Socket.IO**.

![Node.js](https://img.shields.io/badge/Node.js-Backend-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-API-000000?logo=express&logoColor=white)
![Socket.IO](https://img.shields.io/badge/Socket.IO-Realtime-010101?logo=socketdotio&logoColor=white)
![API Testing](https://img.shields.io/badge/API%20Testing-Postman-FF6C37?logo=postman&logoColor=white)

</div>

---

## 📌 Overview

**Secure Connect Platform** is a backend project that brings together REST API operations for notes and real-time communication through Socket.IO. The tested flows shown in this repository cover creating, retrieving, updating, and deleting notes, receiving a note-created event, joining a chat room, and sending chat messages.

## ✨ Features

- 🔑 **Token-based authorization** for protected note requests using a Bearer Token.
- 📝 **Create notes** with a title and content.
- 📚 **Retrieve notes** through the notes API.
- ✏️ **Update notes** by note ID.
- 🗑️ **Delete notes** by note ID.
- ⚡ **Real-time note notifications** using the `note:created` Socket.IO event.
- 💬 **Room-based real-time chat** using `join_room` and `chat_message` events.
- 🧪 **API and socket testing** demonstrated using Postman.

## 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime for the backend |
| Express.js | HTTP API and route handling |
| MongoDB | Persistent note data (as reflected by the returned document fields) |
| Socket.IO | Real-time events and chat communication |
| bcryptjs | Password-hashing dependency visible in the development environment |
| Postman | REST API and Socket.IO testing |

> The table reflects technologies visible in the provided project screenshots. Add any other libraries only if they are present in the project’s `package.json`.

## 🏗️ API Overview

Base URL used during local testing: `http://localhost:5000`

| Method | Endpoint | Purpose |
|---|---|---|
| `GET` | `/api/notes` | Retrieve notes available to the authenticated user |
| `POST` | `/api/notes` | Create a note |
| `PUT` | `/api/notes/:id` | Update a note by its ID |
| `DELETE` | `/api/notes/:id` | Delete a note by its ID |

### Example request body

```json
{
  "title": "My Note",
  "content": "Note content goes here."
}
```

### Authorization

For protected API requests, select **Bearer Token** in Postman’s Authorization tab and provide a valid token. Keep tokens and secrets private; never commit real credentials to GitHub.

## ⚡ Socket.IO Events

The following events are demonstrated in the supplied tests:

| Event | Direction / purpose | Example payload |
|---|---|---|
| `note:created` | Server notification when a note is created | `{ "userId": "…", "title": "Live Notification Test" }` |
| `join_room` | Client requests to join a chat room | `{ "room": "general" }` |
| `chat_message` | Client sends a room message | `{ "room": "general", "username": "Harsh", "message": "Hello!" }` |

The exact payloads and event names should match the server implementation. The examples above are based on the successful Postman tests shown below.

## 🖼️ Test Evidence

Screenshots are intentionally limited to representative successful requests and events, rather than every repeated test.

### 1. Create a note · `201 Created`

![Create note request and response](screenshots/note-create.jpg)

### 2. Update a note · `200 OK`

![Update note request and response](screenshots/note-update.jpg)

### 3. Delete a note · `200 OK`

![Delete note request and response](screenshots/note-delete.jpg)

### 4. Real-time note notification

![Socket.IO note-created event](screenshots/socket-note-created.jpg)

### 5. Join a room and send a chat message

![Socket.IO room join](screenshots/socket-room-join.jpg)

![Socket.IO chat message](screenshots/socket-chat-message.jpg)

### Server-side event logs

![Server logs showing note and chat events](screenshots/server-events.jpg)

## 🚀 Run Locally

1. **Clone the repository.**

   ```bash
   git clone <your-repository-url>
   cd <repository-folder>
   ```

2. **Install dependencies.**

   ```bash
   npm install
   ```

3. **Configure environment variables.** Create a `.env` file and add the variables required by your project, such as your MongoDB connection string and authentication secret. Use the exact variable names expected by your source code. Do not commit `.env`.

4. **Start the server** using the script defined in `package.json`. For example, if your project has a `dev` script:

   ```bash
   npm run dev
   ```

   The supplied terminal screenshot shows the server listening at `http://localhost:5000`.

5. **Test the endpoints and socket events** in Postman using the endpoint table and event names above. Keep the Socket.IO connection open while testing real-time events.

## 🔒 Security Notes

- Store secrets and database credentials in environment variables.
- Do not share or commit Bearer Tokens.
- Validate request bodies and authorize users before reading or modifying their notes.
- Ensure users can access only the data permitted by the application’s authorization logic.

## ✅ Verification Summary

The supplied screenshots show successful responses for note creation (`201 Created`), note update (`200 OK`), note deletion (`200 OK`), a `note:created` notification, room joining, and chat message events. The notes list screenshot returned an empty array at that moment, so it is not included as a showcase image.

---

<div align="center">

**Built to practise secure API workflows and real-time communication.** ⚡

</div>
