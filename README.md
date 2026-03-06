# ⚡ SmartElectro AI – Telegram AI Smart Electronics Store

An **AI-powered Telegram shopping assistant** built using **n8n, Groq AI, Google Sheets, and Gmail**.  
The system allows customers to browse and purchase **smart electronics products** through a conversational chatbot.

Shop owners maintain product inventory in **Google Sheets**, while the AI assistant automatically handles:

- Product discovery
- Customer interaction
- Order placement
- Order storage
- Email confirmation

---

# 🚀 Project Overview

**SmartElectro AI** is an automated product selling system where customers interact with a **Telegram chatbot** to browse and order **smart electronics products**.

The chatbot uses **Groq AI (LLM)** to understand user queries and guide them through the shopping process.

All product data is dynamically fetched from **Google Sheets**, ensuring that the shop owner can easily update product listings without modifying the workflow.

Once an order is confirmed:

1. Customer information is collected
2. The order is stored in **Google Sheets**
3. A **confirmation email** is sent automatically

---

# 🧰 Technology Stack

| Component | Technology |
|-----------|-----------|
| Automation | n8n |
| AI Model | Groq (Llama 3.3 70B) |
| Messaging Platform | Telegram Bot API |
| Product Database | Google Sheets |
| Order Database | Google Sheets |
| Email Service | Gmail Node (n8n) |

---

# 🏗 System Architecture


Customer
↓
Telegram Bot
↓
n8n Workflow
↓
Groq AI Agent
↓
Google Sheets (Products)
↓
Order Processing
↓
Google Sheets (Orders)
↓
Gmail Confirmation Email


---

# ⚙️ System Setup

## 1️⃣ Telegram Bot Configuration

### Step 1: Create a Telegram Bot

1. Open Telegram and search for **@BotFather**
2. Run the command:


/newbot


3. Provide:

- Bot Name
- Bot Username

Example:


SmartElectro AI Bot
smartelectro_ai_bot


4. BotFather will provide a **Bot Token**

Example:


123456789:ABCxyzTOKEN


### Step 2: Connect Bot to n8n

1. Open **n8n**
2. Add **Telegram Trigger Node**
3. Paste the **Bot Token**
4. Set updates to:


message


5. Activate the workflow

---

# 📊 Google Sheets Setup

Two Google Sheets tabs are required.

---

## 1️⃣ Product Sheet

Create a sheet named:


Products


Columns:

| Product ID | Product Name | Category | Price | Stock Status | Description | Image URL | Specifications |
|------------|-------------|----------|------|-------------|-------------|-----------|---------------|

Example:

| Product ID | Product Name | Category | Price | Stock Status | Description | Image URL | Specifications |
|------------|-------------|----------|------|-------------|-------------|-----------|---------------|
| P001 | WavePlay Pro Smartwatch | Smart Watch | 24500 | In Stock | AMOLED smartwatch with health tracking | image_url | AMOLED, Heart Rate, 5 Day Battery |

---

## 2️⃣ Orders Sheet

Create another sheet tab named:


Orders


Columns:

| Order Id | Customer Name | Email | Products |
|----------|--------------|------|----------|

---

## Connecting Google Sheets to n8n

1. Add **Google Sheets Node**
2. Select **OAuth2 Authentication**
3. Connect your Google account
4. Select your spreadsheet
5. Choose the required sheet tab

Example nodes:

- **Products Sheet Node**
- **Add Order Node**

---

# 📧 Email Configuration

The system sends a confirmation email after a successful order.

### Steps:

1. Add **Gmail Node**
2. Connect Gmail using **OAuth2**
3. Configure fields:

| Field | Value |
|------|------|
| To | Customer Email |
| Subject | Order Confirmed |
| Message | HTML Email Template |

The email contains:

- Customer Name
- Order ID
- Order Date
- Purchased Product

---

# 🔄 Workflow Setup

## Importing the Workflow

1. Open **n8n Dashboard**
2. Click **Import Workflow**
3. Upload the provided:


workflow.json


4. Save the workflow

---

# 🔑 Environment Variables

The following credentials must be configured in n8n:

| Service | Required |
|-------|---------|
| Telegram Bot API | Bot Token |
| Groq API | Groq API Key |
| Google Sheets | Google OAuth |
| Gmail | Gmail OAuth |

Example Groq configuration:


Model: llama-3.3-70b-versatile


---

# ▶️ Running the System

### Step 1

Activate the workflow in **n8n**

### Step 2

Open Telegram and start the bot


/start


### Step 3

Interact with the chatbot to browse products and place orders.

---

# 💬 Example Telegram Interaction

### Product Discovery

User:


Ki ki electronics products ache?


Bot:


আমাদের কাছে এই ক্যাটাগরির পণ্যগুলো আছে:

• Smart Watch
• Wireless Earbuds
• Smart Speakers

কোন ক্যাটাগরি দেখতে চান?


---

### Product Request

User:


Smart watch dekhao


Bot:


Smart Watch ক্যাটাগরিতে এই পণ্যটি আছে:

WavePlay Pro Smartwatch
Price: 24,500 BDT
AMOLED Display, Heart Rate Monitor


---

### Product Details

User:


WavePlay Pro show koro


Bot:

Shows product image and description.

---

### Order Placement

User:


Order korte chai


Bot:


অর্ডার করার জন্য আপনার নাম দিন।


Bot collects:

- Name
- Email
- Product

---

### Order Confirmation

Bot:


🎉 Congratulations! Your order has been successfully placed.

Order ID: ORD-1024
Product: WavePlay Pro Smartwatch

A confirmation email has been sent to your email address.


---

# 📦 Deliverables

The project repository contains:


📁 SmartElectro-AI
│
├── workflow.json
├── README.md
└── documentation


---

# ✅ Features

✔ AI conversational product assistant  
✔ Dynamic product database via Google Sheets  
✔ Automated order recording  
✔ Automatic email confirmation  
✔ Multi-language support (English & Bengali)  
✔ Modular n8n workflow

---

# 📌 Evaluation Criteria

The system is evaluated based on:

- Telegram chatbot functionality
- Google Sheets integration
- Automated order processing
- Email confirmation system
- Workflow reliability
- Documentation quality

---

# 👨‍💻 Author

**Hridoy Chandra Das**
