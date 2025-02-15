# 🚀 SolBot - Solana Trading Bot

Welcome to **SolBot** – a high-speed, Telegram-integrated trading bot for the **Solana blockchain**. SolBot is designed for **fast trade execution, copy trading, and automation**, making trading on Solana easier and more efficient.

---

## 📌 Features

- **🚀 Fast Trade Execution** – Optimized for low latency.
- **📲 Trade via Telegram** – No complicated UI, just commands.
- **📈 Copy Trading** – Automatically mimic successful wallets.
- **🛑 Stop-Loss & Limit Orders** – Protect your trades.
- **💰 Dollar-Cost Averaging (DCA)** – Smart investment strategy.
- **🤖 Sniper & Auto Buy/Sell** – Fast reaction to market movements.
- **🔒 Secure Wallet System** – No keys stored in configs.
- **📦 Dockerized Deployment** – Simple and scalable.
- **🔄 Dry-Run Mode** – Simulate trades without real funds.
- **📊 Admin UI & Discord Bot** – Manage settings & analytics.

---

## 🛠️ Getting Started

This guide will help you set up **SolBot** from scratch. If you're a **beginner**, don’t worry! Follow these steps carefully.

---

### 1️⃣ **Set Up a Solana Wallet**
SolBot requires a **Solana wallet** to execute trades. Each user **sets their own wallet inside Telegram**, so no wallet addresses are stored in the `.env` file.

#### **Create Your Trading Wallet**
1. Install **Phantom Wallet** (recommended)  
   - [Download Phantom](https://phantom.app/)
   - Set up your wallet and **write down your recovery phrase** somewhere safe.
   - Get your **wallet address** (click on your wallet, copy the address).

2. Fund Your Wallet  
   - Buy **SOL** from an exchange (e.g., Binance, Coinbase).
   - Withdraw SOL to your Phantom wallet address.

---

### 2️⃣ **Create a Fee Collection Wallet (Admin Only)**
SolBot charges a **1% fee per trade** (or **0.9% for referrals**). These fees need to be collected in a **separate fee wallet**.

#### **How to Create a Fee Wallet**
- The **fee collection wallet** should be a dedicated Solana wallet.
- You can create a new wallet in **Phantom** or **Solflare**.
- This wallet **must be set by the admin** using the **Admin UI or Admin Telegram bot**.

#### **Setting the Fee Wallet**
1. Open the **Admin UI** or **Admin Telegram Bot**.
2. Run the command:
   ```
   /setfeewallet <wallet_address>
   ```
3. The bot will confirm that the **fee wallet has been updated**.

---

### 3️⃣ **Create a Telegram Bot using BotFather**
SolBot operates through Telegram. You need to create a bot:

1. Open Telegram and search for **BotFather**  
   - [Click here to open BotFather](https://t.me/BotFather)

2. Start a conversation and type:  
   ```
   /newbot
   ```
   - Choose a name for your bot (e.g., `SolBot`).
   - Choose a **username** (must end with "bot", e.g., `SolBotTraderBot`).
   - **Copy the API Token** provided by BotFather.

---

### 4️⃣ **Install & Run SolBot**
SolBot runs inside **Docker**. Follow these steps:

#### **🔧 Install Docker**
- [Download Docker](https://www.docker.com/get-started) and install it.
- Verify installation:
  ```bash
  docker --version
  ```

#### **📦 Clone SolBot & Set Up**
1. Open your terminal and run:
   ```bash
   git clone https://github.com/yourusername/solbot.git
   cd solbot
   ```

2. **Start the bot**:
   ```bash
   docker-compose up --build
   ```

---

## 📜 How to Use SolBot

Once SolBot is running, **open Telegram and start your bot**.

### ✅ **Basic Commands**
- **Buy tokens**:
  ```
  /buy <TOKEN> <AMOUNT>
  Example: /buy SOL 1
  ```
- **Sell tokens**:
  ```
  /sell <TOKEN> <AMOUNT>
  Example: /sell SOL 0.5
  ```
- **Copy trade a wallet**:
  ```
  /copytrade <WALLET_ADDRESS>
  Example: /copytrade 7GhF9...xyz
  ```
- **Set stop-loss**:
  ```
  /stoploss <TOKEN> <PRICE>
  Example: /stoploss SOL 90
  ```
- **Enable dry-run mode** (test without real funds):
  ```
  /dryrun on
  ```
- **Check wallet balance**:
  ```
  /balance
  ```

---

## 🛠️ Fee Management (Admin Only)

Fees are collected from trades and sent to the **fee wallet**.

### **Managing Fees via Admin UI**
- Log into the **Admin UI**.
- View **collected fees**, total trades, and analytics.
- Withdraw **fees from the fee wallet** as needed.

### **Managing Fees via Discord**
- The **Admin Discord Bot** provides real-time updates on:
  - Total collected fees.
  - Withdrawal notifications.
  - Security warnings.
- You can set alerts for **fee balance thresholds**.

---

## 🔮 Roadmap

✅ **Phase 1:** Core Bot Development  
✅ **Phase 2:** Admin UI, Trade Analytics, Discord Bot  
🔜 **Phase 3:** AI-Powered Trading  

---

## 🔐 Proprietary License

**Copyright (c) 2025 SolBot Developer**

All rights reserved.

This software is proprietary and cannot be copied, modified, or redistributed without explicit permission from the original developer.

By using this software, you agree to the following terms:
- Personal use is permitted.
- Commercial use (reselling, offering as a service) is strictly **prohibited** without a separate license.
- Reverse engineering or modifying the software is not allowed.

For inquiries about commercial licensing, contact the developer.

---

## 🤝 Contributing

At this time, SolBot is **not open-source**. If you wish to contribute or request a feature, feel free to open an issue on GitHub.

---

## ❓ Need Help?
If you run into any issues:
1. **Check your Solana wallet connection** inside Telegram.
2. **Make sure your Solana wallet is funded**.
3. **Verify your Telegram bot token is correct**.
4. **Restart the bot** with:
   ```bash
   docker-compose down
   docker-compose up --build
   ```

---

## 🔥 Summary of Key Changes
✅ **Wallets are set by users inside Telegram** (not stored in `.env`).  
✅ **Admin can set the fee collection wallet** via the **Admin UI or Admin Telegram Bot**.  
✅ **Fee management is handled via the Admin UI & Discord notifications**.  
✅ **Admin Telegram Bot is separate from SolBot** (for security & management).  

🚀 **This ensures better security, flexibility, and scalability for SolBot!** 🔥

