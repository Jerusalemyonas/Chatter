**Real-Time Messaging Platform (WP7)**

A high-performance, containerized instant messaging application built for the **Web Programming Project**. This platform features a premium glassmorphic UI, real-time communication, and industry-standard security.

Developed by: Eyerusalem Yonas Lemma

---

# Features

- **Premium Glassmorphic UI**: A stunning, responsive interface designed with React and Vanilla CSS.
- **AES-256 Symmetric Encryption**: Client-side encryption ensures that messages are stored as gibberish in the database, providing true user privacy.
- **Real-time Interaction**: Instant message delivery, typing indicators, and read receipts powered by **Socket.io**.
- **Telegram-Style Emojis**: Huge, animated emojis (heartbeat and pop-in effects) for a more expressive experience.
- **Message Management**: Ability to edit messages after sending them.
- **User Notifications**: Unread message badges in the sidebar.
- **Full Mobile Responsiveness**: A seamless experience across mobile, tablet, and desktop devices.
- **Dockerized Stack**: Fully containerized environment for consistent deployment.

---

# Tech Stack

- **Frontend**: React (Vite), Lucide Icons, Crypto-JS (for encryption), Date-fns.
- **Backend**: Node.js, Express, Socket.io, TypeScript.
- **Database**: PostgreSQL with Prisma ORM.
- **DevOps**: Docker & Docker Compose.

---

# 1. Clone the repository

```bash
git clone https://github.com/Fikresilase/chatter.git
cd chatter
```

# 2. Run with Docker

```bash
docker-compose up -d --build
```

# 3. Access the Application

- **Frontend**: [http://localhost:5173](http://localhost:5173)
- **Backend**: [http://localhost:3000](http://localhost:3000)
- **PostgreSQL**: Maps to port `5431` on your host.

The containers will handle the following automatically:

- Spinning up the PostgreSQL database.
- Running database migrations.
- Building the TypeScript backend and React frontend.
- Starting all services in sync.

---

# The "Security Reveal"

1.  Open the app and send a message: `"Hello Professor, this is encrypted!"`
2.  Open your terminal and run:
    ```bash
    docker exec -it chatter-postgres-1 psql -U postgres -d chatdb -c "SELECT content FROM \"Message\";"
    ```
3.  **The result** will be an encrypted string (e.g., `U2FsdGVkX1...`). This proves that even if the database is hacked, the messages remain private.

---

# Project Structure

```text
├── backend/
│   ├── prisma/             # Database schema and migrations
│   ├── src/                # Express & Socket.io logic
│   ├── Dockerfile          # Multi-stage production build
│   └── entrypoint.sh       # Auto-migration script
├── frontend/
│   ├── src/                # React components & UI
│   ├── src/utils/crypto.ts # Client-side AES logic
│   └── Dockerfile          # Vite production build
└── docker-compose.yml      # Service orchestration
```

---

# Authorship

**Eyerusalem Yonas**  
Web Programming Project - 2026_
