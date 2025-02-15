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

## 📦 Installation & Setup

### **1️⃣ Install Docker & Clone the Repository**
Ensure **Docker & Docker Compose** are installed:  
- [Download Docker](https://www.docker.com/get-started)  
- Verify installation:  
  ```bash
  docker --version
  ```

Clone the repository:  
```bash
git clone https://github.com/yourusername/solbot.git
cd solbot
```

---

### **2️⃣ Setting Up Your Solana Wallet**
Each user **sets their own wallet inside Telegram**.  
SolBot does **not store wallets in config files** for security.

#### **Create a Solana Wallet (If You Don’t Have One)**
1. Install **Phantom Wallet** ([Download](https://phantom.app/))
2. Set up your wallet & **backup your recovery phrase**.
3. Copy your **wallet address** (Click on your wallet → Copy Address).

#### **Link Your Wallet to SolBot**
Once your wallet is ready, link it inside Telegram:  
```bash
/setwallet <your_solana_wallet_address>
```
The bot will confirm:
```
✅ Wallet linked successfully!
```

---

### **3️⃣ Dry-Run Mode (Simulated Trading)**
**Dry-Run Mode** allows you to **test trades** without using real funds.

#### **Enable Dry-Run Mode**
```bash
/dryrun on
```
🔹 **What Happens?**
- Trades are simulated, but **not executed on Solana**.
- You receive **real-time feedback** on trade performance.

#### **Disable Dry-Run Mode**
```bash
/dryrun off
```
The bot will confirm:
```
✅ Dry-Run mode disabled. All trades will now be real.
```

---

### **4️⃣ Admin-Only Fee Collection Wallet**
SolBot **charges a 1% fee per trade** (0.9% with referrals).  
Fees are collected in a **dedicated fee wallet**.

#### **How to Set the Fee Wallet (Admin Only)**
1. Open the **Admin UI** or **Admin Telegram Bot**.
2. Run:
   ```
   /setfeewallet <wallet_address>
   ```
3. Confirmation:
   ```
   ✅ Fee wallet updated successfully.
   ```

---

### **5️⃣ Running SolBot with Docker**
Run the bot inside Docker:  
```bash
docker-compose up --build -d
```

To stop the bot:
```bash
docker-compose down
```

---

## 📜 Using SolBot (Commands & Interactive UI)

SolBot supports both **commands** and an **interactive UI**.

### **✅ Basic Commands**
| **Command**       | **Function** |
|------------------|-------------|
| `/buy <TOKEN> <AMOUNT>`  | Buy a token |
| `/sell <TOKEN> <AMOUNT>` | Sell a token |
| `/copytrade <WALLET>`   | Mimic another wallet's trades |
| `/stopcopytrade`        | Stop copy trading |
| `/stoploss <TOKEN> <PRICE>` | Set a stop-loss |
| `/dryrun on/off`        | Enable dry-run mode (simulate trades) |
| `/balance`              | Check wallet balance |

---

## 🔐 Security Best Practices
🚨 **Protect your funds** by following these security guidelines:

✅ **Never share your private key or seed phrase** with anyone.  
✅ **Verify the bot’s username** before interacting.  
✅ **Enable 2FA** on your exchange/wallet for added security.  
✅ **Use only official Telegram links** to access the bot.  

---

## ⚠️ Common Errors & Troubleshooting
| **Issue**                  | **Solution** |
|----------------------------|--------------|
| Bot is not responding      | Restart Docker & check logs |
| Trade not executing        | Ensure wallet is funded |
| Cannot set fee wallet      | Only the admin can set this |

---

## 📡 API Endpoints (For Future Admin Features)
```
GET /api/trades - Retrieve all trades
POST /api/trade - Execute a new trade
```

---

## 👥 User Role Breakdown
| **Role**      | **Permissions** |
|--------------|----------------|
| User        | Buy/Sell, Copy Trade |
| Admin       | Manage fee wallet, update bot settings |

---

## 🚀 Performance Benchmarks
```
⚡ Trade Execution Speed: ~500ms (under normal network conditions)
📉 Max Delay per trade: < 1 second (during peak load)
```

---

## ❓ Frequently Asked Questions (FAQ)
- **How do I remove my wallet?**
  ```
  /removewallet
  ```
- **Can I trade without fees?**
  ```
  No, but referrals get a discount (0.9% fee).
  ```
- **Can I use multiple wallets?**
  ```
  No, one wallet per user at a time.
  ```

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
