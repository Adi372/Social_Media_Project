# A Social Media Platform with AI Chat

<img width="1535" height="1024" alt="Image" src="https://github.com/user-attachments/assets/da0e935f-8a13-4deb-966d-4b6134db2bec" />

<img width="1918" height="908" alt="Image" src="https://github.com/user-attachments/assets/c6bd2ced-c6b2-4af3-898c-011d8ca63ad0" />

<img width="1917" height="912" alt="Image" src="https://github.com/user-attachments/assets/50502eae-5115-413d-b5fb-653685a15c90" />

<img width="1917" height="916" alt="Image" src="https://github.com/user-attachments/assets/0370fa82-d0b1-415b-bcb2-66d36b6945e6" />

<img width="1917" height="912" alt="Image" src="https://github.com/user-attachments/assets/3516cc45-9291-4979-a81f-d9622e85d731" />

<img width="1915" height="910" alt="Image" src="https://github.com/user-attachments/assets/77e8e8d9-5037-4f6c-9f24-6c52c0dc590f" />

<img width="1918" height="917" alt="Image" src="https://github.com/user-attachments/assets/d841ae2a-6720-4e56-9ced-7131a47d580d" />

> 🚧 **Project Status:** This project is currently under active development. Features, APIs, UI components, and documentation may change as development continues.

[**Live Link**](https://void-tup9.onrender.com/)

Since the platform still has a few bugs and some features may run slowly, so I'm sharing this quick tutorial to help you navigate these issues and get the best experience possible

**For Desktop Users:**

https://github.com/user-attachments/assets/8ae2c3dc-577e-4b43-a9a9-93ec3d602ae9

**For Mobile Users:**

https://github.com/user-attachments/assets/c400e7c7-dd71-419d-ba60-aa8fe15ac81a

## Overview
A full-stack social media application featuring user authentication, social posting, friendships, notifications, real-time messaging, and an AI-powered chat assistant with long-term memory using embeddings and vector search.

---

# Tech Stack

## Frontend
- React
- Vite
- React Router
- Axios
- Socket.IO Client
- Tailwind CSS

## Backend
- Node.js
- Express.js
- Mongoose
- JWT Authentication
- Cookie-based Authentication
- Multer
- Socket.IO

## Database
- MongoDB (via Mongoose)

## AI & RAG Services
- LangChain Agent
- Google GenAI Embeddings
- Pinecone Vector Database
- ImageKit Media Storage

---

# Key Features

## Authentication & User Management
- User registration
- Login & logout
- Account deletion
- Profile management

## Social Media Features
- Create posts with image uploads
- View social feed
- Like posts
- Comment on posts
- Save/unsave posts

## Friend System
- Send friend requests
- Accept/reject requests
- Unsend requests
- Remove friends

## Notifications
- Like notifications
- Comment notifications
- Friend request notifications
- Friend acceptance notifications
- Clear notifications

## Real-Time Chat
- One-to-one messaging
- Socket.IO powered communication
- Live message delivery
- Message notifications

## AI Chat Assistant
- Long-term memory using embeddings
- Pinecone vector retrieval
- Context-aware conversations
- Persistent AI chat history

## User Discovery & Personalization
- Interest-based account suggestions
- Edit profile details
- Manage interests

---

# Project Structure

```text
.
├── Backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── models/
│   │   ├── middlewares/
│   │   ├── services/
│   │   ├── sockets/
│   │   └── db/
│   ├── server.js
│   └── package.json
│
├── Frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── utils/
│   │   └── ...
│   ├── vite.config.js
│   └── package.json
│
├── Social Media UI/
│   └── Design Assets
│
└── README.md
```

---

# Configuration

## Backend
- package.json
- package-lock.json
- .gitignore
- server.js

## Frontend
- package.json
- package-lock.json
- vite.config.js
- eslint.config.js
- .gitignore
- index.html

Environment files are excluded from version control and must be created locally.

---

# Available Scripts

## Frontend

```bash
npm run dev
npm run build
npm run lint
npm run preview
```

## Backend

Currently only contains a placeholder test script:

```bash
npm test
```

Recommended additions:

```bash
npm run dev
npm start
```

---

# Backend Dependencies

- @google/genai
- @langchain/groq
- @pinecone-database/pinecone
- bcryptjs
- cookie-parser
- cors
- dotenv
- express
- imagekit
- jsonwebtoken
- langchain
- mongoose
- multer
- socket.io
- uuid

# Frontend Dependencies

- @tailwindcss/vite
- axios
- react
- react-dom
- react-router-dom
- socket.io-client
- tailwindcss

---

# API Endpoints

## Authentication
Base Route: `/api/auth`

- POST `/register`
- POST `/login`
- DELETE `/delete`
- GET `/findUser`
- POST `/logout`

## Posts
Base Route: `/api/post`

- POST `/create`
- DELETE `/deletePost`
- GET `/allPosts`
- GET `/myPosts`
- POST `/like`
- POST `/comment`
- POST `/removeLike`
- POST `/removeComment`
- POST `/save`
- POST `/unsave`
- GET `/userPosts`
- GET `/likedPosts`
- GET `/commentedPosts`
- GET `/savedPosts`

## Chats
Base Route: `/api/chat`

- POST `/findOrCreate`
- DELETE `/deleteMessage`
- DELETE `/deleteChat`
- GET `/loadMessages`
- GET `/allChats`
- GET `/allRealChats`

## Users
Base Route: `/api/user`

Includes:
- Search users
- Friend management
- Block management
- Notifications
- Profile management
- Interest management

## AI Chat
Base Route: `/api/aiChat`

- POST `/findOrCreate`
- GET `/loadAIMessages`

---

# Socket Events

## Chat Events

### Client → Server
- join-chat
- send-message

### Server → Client
- receive-message
- new-message-notification

## AI Chat Events

### Client → Server
- join-aiChat
- user-response

### Server → Client
- ai-response

---

# Authentication Flow

1. User registers or logs in.
2. JWT token is generated.
3. Token is stored in an HTTP-only cookie.
4. Authentication middleware validates requests.
5. Socket connections authenticate using the same JWT cookie.

---

# Database Models

## User Model
Stores:
- Profile information
- Username
- Email
- Password
- Interests
- Friends
- Friend requests
- Blocked users
- Posts
- Likes
- Comments
- Saves
- Notifications

## Post Model
Stores:
- Owner
- Caption
- Image
- Username snapshot
- Likes
- Comments
- Shares
- Saves

## Chat Model
Stores:
- Participants
- Hidden users
- Group flag
- Last message

## Message Model
Stores:
- Chat ID
- Sender
- Sender profile picture
- Message text
- Soft delete status

## AI Chat Model
Stores:
- User chat metadata
- Last message

## AI Message Model
Stores:
- Message content
- Message role

---

# Highlights

- Full-stack MERN architecture
- Real-time communication using Socket.IO
- AI-powered conversational assistant
- Vector search using Pinecone
- Secure JWT authentication
- Interest-based social discovery
- Media uploads with ImageKit

---

# Future Improvements

- Group chats
- Voice/video calling
- Advanced AI agents
- Small 2d metaverse
---
