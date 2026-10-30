# Secure Connect and Communication Platform

Starter project for **Web Dev III, Lab 4**. It is a backend application, not a frontend website. The assignment's expected evidence is API testing (for example, Postman) and real-time chat activity in the server terminal.

## Requirements covered in this project

- Signup and login with bcrypt password hashing
- JWT token generation and verification
- Protected API routes
- Notes CRUD scoped to the authenticated user
- Basic role-based access control (RBAC): signup users default to `user`; an `admin` role can access the admin route
- Real-time chat using Socket.IO
- Node.js EventEmitter events for signup, login, note creation and chat messages
- Environment variables using dotenv

## 1. Open the project

1. Extract the ZIP.
2. Open the `secure-connect-platform` folder in VS Code.
3. Ensure Node.js and npm are installed.
4. Copy `.env.example` to a new file named `.env`.
5. Change `JWT_SECRET` to a long random secret.

## 2. Database setup

This project uses the official MongoDB Node.js driver. Start a local MongoDB server, or use a MongoDB Atlas connection string.

Set `MONGODB_URI` in `.env`:
- Local: `mongodb://127.0.0.1:27017`
- Atlas: paste your connection string, keeping credentials private.

Set `DB_NAME=secure_connect_platform`.

## 3. Install and run

In the VS Code terminal, from this folder:

```bash
npm install
npm run dev
```

Or use `npm start`.

The server should report that it is listening on the configured port after it connects to MongoDB.

## 4. Test in Postman

Base URL: `http://localhost:5000`

### Signup
`POST /api/auth/signup`
```json
{
  "username": "victor",
  "email": "victor@example.com",
  "password": "StrongPassword123"
}
```

### Login
`POST /api/auth/login`
```json
{
  "email": "victor@example.com",
  "password": "StrongPassword123"
}
```
Copy the returned `token`.

For protected requests, add this header:
`Authorization: Bearer YOUR_TOKEN_HERE`

### Notes API
- `GET /api/notes` - list your notes
- `POST /api/notes` - create a note with `{"title":"My First Note","content":"Hello"}`
- `GET /api/notes/:id` - read one of your notes
- `PUT /api/notes/:id` - update one of your notes
- `DELETE /api/notes/:id` - delete one of your notes

### Protected route and RBAC
- `GET /api/protected` - requires a valid JWT
- `GET /api/admin` - requires a valid JWT and `admin` role

For safety, public signup always assigns the `user` role. To test admin-only access in a lab database, update that user's `role` field to `admin` in MongoDB, then log in again to receive a token containing the updated role.

### Real-time chat
Use a Socket.IO client (or a small local test page/client) to connect to `http://localhost:5000`. Emit `join_room` with `{ "room": "general" }`, then emit `chat_message` with `{ "room": "general", "username": "victor", "message": "Hello!" }`. The server logs connections and messages. This starter logs the provided username for classroom demonstration; production chat should derive identity from a verified socket token.

## Important notes

- No frontend UI is required by the assignment PDF.
- Do not commit `.env` or real credentials to GitHub.
- This is a learning/lab implementation, not production-hardened authentication.
- Before submission, test every endpoint and capture evidence of successful signup/login, unauthorized access being blocked, notes CRUD, and Socket.IO messages.
