# C1 — Multi-Instance Chat

> A scalable real-time chat backend built to explore distributed systems, cross-instance communication, shared presence, and fault tolerance as part of **DOOMSDAY — Track C**.

![Node.js](https://img.shields.io/badge/Node.js-20%2B-339933?logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white)
![WebSockets](https://img.shields.io/badge/WebSockets-Real--Time-010101?logo=socketdotio&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-Pub%2FSub-DC382D?logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?logo=postgresql&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-Load_Balancing-009639?logo=nginx&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?logo=docker&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-Testing-6E9F18?logo=vitest&logoColor=white)
![k6](https://img.shields.io/badge/k6-Load_Testing-7D64FF?logo=k6&logoColor=white)

---

## Features & Highlights

- **Multi-Instance Architecture:** Run multiple backend instances behind a load balancer.
- **Real-Time Messaging:** Exchange messages over persistent WebSocket connections.
- **Cross-Instance Communication:** Deliver messages between users connected to different instances using Redis Pub/Sub.
- **Shared Presence:** Track online users across server instances.
- **Offline Message Delivery:** Persist messages for recipients who are temporarily disconnected.
- **Duplicate Prevention:** Use idempotency mechanisms to prevent duplicate message processing.
- **Fault Tolerance:** Handle server restarts, reconnections, and instance failures.
- **Observability:** Monitor connections, throughput, errors, and message latency.
- **Load Testing:** Evaluate performance under concurrent connections and sustained traffic.

## Tech Stack

| Technology | Purpose |
|---|---|
| Node.js + TypeScript | Backend runtime and type-safe development |
| WebSockets (`ws`) | Real-time, bidirectional communication |
| Redis | Pub/Sub and shared presence |
| PostgreSQL | Persistent messages and delivery state |
| Nginx | Load balancing |
| Docker Compose | Local multi-service environment |
| Vitest | Unit and integration testing |
| k6 | Load and performance testing |

## Architecture

```text
                 Chat Clients
                      |
                 Load Balancer
                    (Nginx)
                      |
          +-----------+-----------+
          |           |           |
       Server A    Server B    Server C
          |           |           |
          +-----------+-----------+
                      |
              +-------+-------+
              |               |
            Redis         PostgreSQL
          Pub/Sub          Persistence
          Presence         Message State
```

## Getting Started

### Prerequisites

- Node.js
- pnpm
- Docker and Docker Compose
- Git

### Setup

```bash
git clone <your-repository-url>
cd c1-multi-instance-chat
pnpm install
```

Start the required infrastructure:

```bash
docker compose up -d
```

Run the development server:

```bash
pnpm dev
```

*Setup commands will be updated as the project implementation progresses.*

## Project Goals

This project focuses on understanding and implementing:

- Distributed communication between backend instances
- Message persistence and delivery semantics
- Shared state and presence management
- Idempotency and concurrency
- Failure recovery and reconnection
- Performance measurement and system reliability

## Project Status

**Status:** In Development

Part of the **DOOMSDAY Track C** program.

