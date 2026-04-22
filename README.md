# 🚀 Relay Chat App

> **Relay** is a premium, real-time communication platform built with the modern web stack. It provides a seamless, secure, and highly responsive chat experience with support for direct messaging, group conversations, and real-time status updates.

---

### ⚠️ Important Recommendations & Notes

> [!IMPORTANT]
> **Environment Configuration**: Ensure you have a `.env` file with `DATABASE_URL` (Neon PostgreSQL), `JWT_SECRET`, and `CLOUDINARY_*` credentials before running the app.

> [!TIP]
> **Prisma 7 Compatibility**: This project uses **Prisma 7**. Unlike older versions, the `url` property is managed in `prisma.config.ts`, not in `schema.prisma`. Always use `npx prisma db push` to synchronize your database schema.

> [!WARNING]
> **Connection Timeouts**: Serverless databases like Neon may experience wake-up delays. If you encounter connection errors, ensure your `DATABASE_URL` includes `&connect_timeout=30`.

---

## 📖 Detailed Description

Relay Chat App is designed to solve the complexities of modern real-time communication. Built using **Next.js 16** and **Socket.io**, it offers a custom-built server architecture that enables ultra-low latency messaging. The application leverages **Prisma 7** for efficient database management and **Neon PostgreSQL** for scalable serverless storage. 

The UI is crafted with **Tailwind CSS 4** and **Framer Motion**, ensuring a smooth, "fluid" user experience with glassmorphism aesthetics and responsive layouts. State management is handled globally via **Redux Toolkit**, providing a single source of truth for conversations, messages, and user presence.

---

## ✨ Key Features

- **⚡ Real-time Messaging**: Instant message delivery using Socket.io rooms.
- **👥 Group & Direct Chats**: Seamlessly switch between private 1-on-1 chats and dynamic group conversations.
- **📸 Media Support**: Profile picture uploads and media handling powered by Cloudinary.
- **🛡️ Secure Auth**: JWT-based authentication with Bcrypt password hashing.
- **🤝 Friend System**: Comprehensive friend request workflow (Pending -> Accepted/Rejected).
- **🟢 Live Presence**: Real-time "Online" status tracking for all users.
- **✅ Read Receipts**: Track when your messages are seen by others.
- **🗑️ Message Management**: Supports "Delete for me" and "Delete for everyone" functionality.

---

## 🛠️ Tech Stack

### Frontend & Backend
- **Framework**: [Next.js 16 (App Router)](https://nextjs.org/)
- **Runtime**: [Node.js](https://nodejs.org/) with `tsx` custom server
- **Styling**: [Tailwind CSS 4](https://tailwindcss.com/), [Lucide React](https://lucide.dev/)
- **Animations**: [Framer Motion](https://www.framer.com/motion/)
- **State Management**: [Redux Toolkit](https://redux-toolkit.js.org/)

### Database & Infrastructure
- **ORM**: [Prisma 7](https://www.prisma.io/)
- **Database**: [Neon PostgreSQL](https://neon.tech/)
- **Real-time**: [Socket.io](https://socket.io/)
- **Storage**: [Cloudinary](https://cloudinary.com/)

---

## 🚀 Getting Started

### 1. Clone & Install
```bash
git clone <repository-url>
cd relay-chatapp
npm install
```

### 2. Configure Environment
Create a `.env` file in the root directory:
```env
# Database
DATABASE_URL="postgresql://user:pass@host/db?sslmode=require&connect_timeout=30"

# Authentication
JWT_SECRET="your_secure_secret"

# Socket.io (optional override)
NEXT_PUBLIC_SOCKET_URL="http://localhost:3000"

# Cloudinary
CLOUDINARY_CLOUD_NAME="your_cloud_name"
CLOUDINARY_API_KEY="your_api_key"
CLOUDINARY_API_SECRET="your_api_secret"
```

### 3. Initialize Prisma
```bash
npx prisma generate
npx prisma db push
```

### 4. Run Development Server
```bash
npm run dev
```

---

## 📁 Project Structure

```text
├── prisma/               # Database schema & migrations
├── public/               # Static assets
├── src/
│   ├── app/              # Next.js App Router (Pages & APIs)
│   ├── components/       # Reusable UI components
│   ├── lib/              # Utility functions (Prisma, Cloudinary, etc.)
│   ├── redux/            # State management (Slices & Store)
│   └── middleware.ts     # Auth & Route protection
├── server.ts             # Custom HTTP & Socket.io server
├── tsconfig.json         # TypeScript configuration
└── package.json          # Dependencies & scripts
```

---

## 👤 Development

Developed with ❤️ by **Khuzaima**. 
If you have any questions or feedback, feel free to open an issue or pull request!
