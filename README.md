# 🚀 SolBot - Solana Trading Bot

**SolBot** is a high-speed, **Telegram-integrated trading bot** for the **Solana blockchain**, designed for **fast execution, copy trading, and automation**. SolBot ensures **secure, efficient, and low-latency trading** while offering an intuitive **interactive UI** alongside command-based execution.

---

## 📌 Key Features

✅ **Ultra-Fast Trade Execution** – Optimized for minimal latency.  
✅ **Telegram Bot Interface** – Trade using **commands** or an **interactive UI**.  
✅ **Copy Trading** – Mimic top-performing wallets effortlessly.  
✅ **Stop-Loss & Limit Orders** – Advanced trade management tools.  
✅ **Dollar-Cost Averaging (DCA)** – Smart accumulation strategies.  
✅ **Sniper & Auto Buy/Sell** – Rapid market entry/exit.  
✅ **Integrated Wallet System** – Users set wallets via Telegram, **no keys stored in configs**.  
✅ **Redis-Powered Trade Execution** – Ensures fast, queue-based trading.  
✅ **Admin Dashboard & Discord Notifications** – Manage settings, fees, and analytics.  
✅ **Scalable Microservices Architecture** – Designed for **performance & growth**.  
✅ **Dry-Run Mode** – Simulate trades without using real funds.  

---

## 🛠️ Requirements to Build & Run SolBot

To set up and run SolBot, you will need the following:

### **1️⃣ Solana Wallets (Phantom)**
You will need **two separate wallets**:

✅ **Trading Wallet** (For executing trades)  
   - This is the wallet linked to each user via Telegram.  
   - Users set their own wallets using `/setwallet <wallet_address>`.  

✅ **Fee Collection Wallet** (For collecting trading fees)  
   - This is the **admin-only wallet** that collects the **1% trading fee**.  
   - The admin sets it using `/setfeewallet <wallet_address>`.  

**👉 Recommended Wallets:** [Phantom](https://phantom.app/) or [Solflare](https://solflare.com/).  

---

### **2️⃣ Telegram Bot API Key**
✅ **Create a bot using BotFather** ([Open BotFather](https://t.me/BotFather))  
✅ Run `/newbot` → Choose a name → Copy the **API Token**  
✅ Add this token to the bot environment configuration.

---

### **3️⃣ Docker & Docker Compose**
✅ Install **Docker**: [Download Here](https://www.docker.com/get-started)  
✅ Verify installation:
```bash
docker --version
```
✅ **Clone the repository**:
```bash
git clone https://github.com/yourusername/solbot.git
cd solbot
```
✅ Start the bot:
```bash
docker-compose up --build -d
```

---

### **4️⃣ Solana RPC Node (For Blockchain Access)**
✅ Get a **Solana RPC URL** (e.g., from [QuickNode](https://www.quicknode.com/) or [Alchemy](https://www.alchemy.com/)).  
✅ Add the **RPC URL** to the bot configuration.

---

### **5️⃣ PostgreSQL Database**
✅ SolBot uses a **PostgreSQL database** to store **wallets, trades, and settings**.  
✅ This is **automatically set up via Docker Compose**.

---

### **6️⃣ Redis Queue (For Trade Execution)**
✅ Redis is used for **fast & scalable trade execution**.  
✅ This is **included in Docker Compose**, so no manual setup is needed.

---

### **7️⃣ Admin UI & Discord Bot (For Management)**
✅ **Admin UI** lets you manage **trades, fees, and users**.  
✅ **Discord Bot** provides **real-time alerts** on **trades & fees**.

---

### **🔥 Summary of What You Need**
| **Requirement**     | **Purpose** |
|--------------------|------------|
| **Phantom Wallet (Trading)** | Executes trades for each user |
| **Phantom Wallet (Fees)** | Collects fees from trades (Admin Only) |
| **Telegram Bot API Token** | Allows interaction with Telegram |
| **Solana RPC URL** | Connects the bot to the blockchain |
| **Docker & Docker Compose** | Runs SolBot in a containerized setup |
| **PostgreSQL Database** | Stores user data & trade history |
| **Redis Queue** | Ensures fast trade execution |

---

## 🏗️ Project Structure

```
solbot/
│── admin/                # Admin UI (Settings & Fee Management)
│   ├── Dockerfile        # Dockerfile for the Admin UI
│── api/                  # Backend API for trade execution
│   ├── Dockerfile        # Dockerfile for the API service
│── config/               # Configuration files
│── db/                   # Database (PostgreSQL)
│── docs/                 # Documentation and guides
│── telegram/             # Telegram bot logic (User interaction)
│   ├── Dockerfile        # Dockerfile for the Telegram bot
│── queue/                # Redis queue for task management
│   ├── Dockerfile        # Dockerfile for the Redis queue worker
│── docker-compose.yml    # Containerized deployment setup
```

Each service has **its own Dockerfile**, ensuring **modular, scalable, and efficient containerization**.

---

## 🔮 Future Plans
✅ **Phase 1:** Core Bot Development  
✅ **Phase 2:** Admin UI, Trade Analytics, Discord Bot  
🔜 **Phase 3:** AI-Powered Trading, Advanced Strategies  

---

## 🔐 Proprietary License

**This software is proprietary** and cannot be copied, modified, or redistributed without explicit permission.

For **commercial licensing inquiries**, contact the developer.

---

## ❓ Need Help?
1. **Check your Solana wallet connection** inside Telegram.
2. **Ensure your Solana wallet is funded**.
3. **Verify your Telegram bot token is correct**.
4. **Restart the bot**:
   ```bash
   docker-compose down
   docker-compose up --build -d
   ```

---

🚀 **This README ensures everything is well-documented for smooth onboarding & efficient trading!** 🔥
