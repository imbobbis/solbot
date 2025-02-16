# 📦 SolBot Dependencies

This document outlines all the required dependencies for **SolBot**, including **Python packages, system-level dependencies, and external services**.

---

## **1️⃣ Python Dependencies**
These are the Python packages required to run SolBot. They are listed in `requirements.txt` and can be installed using:
```bash
pip install -r requirements.txt
```

| **Package**           | **Purpose** |
|----------------------|-------------|
| `python-telegram-bot` | Telegram bot API integration |
| `redis`              | Redis client for task queuing |
| `rq`                 | Background task processing |
| `psycopg2`           | PostgreSQL database connection |
| `requests`           | HTTP requests (e.g., for Solana RPC) |
| `solana`             | Solana blockchain interaction |
| `dotenv`             | Load environment variables |
| `fastapi`            | API framework (for admin and web services) |
| `uvicorn`            | ASGI server for FastAPI |

---

## **2️⃣ System Dependencies**
These are **system-level packages** required for running SolBot.

| **Dependency**       | **Purpose** |
|---------------------|-------------|
| `Python 3.10+`      | Required for the bot and API |
| `PostgreSQL 15+`    | Database for storing user settings & trades |
| `Redis`             | Message queue for trade execution |
| `Docker`            | Containerized deployment |
| `Docker Compose`    | Multi-container setup |

If you're running SolBot **without Docker**, install system dependencies manually:
```bash
sudo apt-get update && sudo apt-get install -y python3 python3-pip postgresql redis
```

---

## **3️⃣ External Services**
SolBot connects to **external blockchain services** for real-time trade execution.

| **Service**          | **Purpose** |
|---------------------|-------------|
| **Solana RPC URL**   | Required for blockchain interactions (e.g., from QuickNode, Alchemy) |
| **Telegram Bot API** | Allows Telegram bot functionality |
| **Phantom Wallet**   | Required for trading & fee collection |

---

## **4️⃣ Dockerized Deployment**
If using Docker, **dependencies are installed automatically**.

- **Python packages** are installed via `requirements.txt` inside the `Dockerfile`.
- **PostgreSQL & Redis** are set up via `docker-compose.yml`.

To run everything with Docker:
```bash
docker-compose up --build -d
```

---

## **🛠️ Managing Dependencies**
### **📌 Installing Python Packages**
```bash
pip install -r requirements.txt
```
### **📌 Updating Dependencies**
To update all Python dependencies:
```bash
pip freeze > requirements.txt
```

---

## **🔥 Summary**
| **Category** | **Files Used** |
|-------------|--------------|
| **Python Packages** | `requirements.txt` |
| **System Dependencies** | `Dockerfile`, `DEPENDENCIES.md` |
| **External Services** | `config/.env` (stores API keys) |
| **Database & Queue** | `docker-compose.yml` |

---

🚀 **SolBot is now well-documented with a structured dependencies list!**  
This ensures **easy installation, debugging, and scalability**.

