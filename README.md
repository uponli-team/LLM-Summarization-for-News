# 📰 LLM Financial News Summarization Automation

An automated financial news analysis system built with **n8n**, **Google Gemini (LLM)**, **Telegram Bot**, and **Google Sheets**.

This workflow fetches financial news from multiple RSS feeds, extracts article content, summarizes it using AI, identifies stock tickers and catalysts, and sends structured results to Telegram and Google Sheets.

---

## 🚀 What This Project Does

When triggered from Telegram:

1. Collects financial news from multiple RSS sources
2. Extracts full article content
3. Sends article to Google Gemini LLM
4. Extracts:
   - Stock ticker
   - Sector
   - Primary catalyst
   - Short factual summary (≤200 characters)
   - Market direction (Bullish / Neutral / Bearish)
5. Sends structured result back to Telegram
6. Stores article metadata in Google Sheets

---

## 🧠 AI Prompt Structure

The LLM is instructed to:

- Extract only relevant financial data
- Identify actionable catalysts
- Keep summary under 200 characters
- Avoid opinions or assumptions
- Output in strict structured format:

```
TITLE: <title>
🏷TICKER: <ticker>
🏭 SECTOR: <sector>
⚡CATALYST: <brief catalyst>
📝SUMMARY: <short summary>
Direction: <Bullish | Neutral | Bearish>
```

---

## 📰 News Sources Used

- Yahoo Finance RSS
- Yahoo News Finance
- MarketWatch Top Stories
- Investing.com Financial News
- CNBC RSS

---

## 🔧 Tech Stack

- n8n (Workflow Automation)
- Google Gemini (LLM Chat Model)
- Telegram Bot API
- Google Sheets API
- RSS Feeds
- HTTP Request Node
- Markdown Parser

---

## ⚙️ Workflow Architecture

Telegram Trigger  
→ Extract Message Data  
→ Load RSS Feed List  
→ Loop Through Feeds  
→ Read RSS Items  
→ Limit Articles  
→ Fetch Article Content  
→ Convert HTML to Markdown  
→ Send to Gemini LLM  
→ Format Output  
→  
   ↳ Send to Telegram  
   ↳ Append to Google Sheets  

---

## 📊 Google Sheets Storage

The workflow appends:

- Publication Date
- Title
- Article Text
- Link

This allows tracking and later analysis of processed news.

---

## 🔔 Telegram Integration

- Triggered via Telegram message
- Returns structured AI summary
- Silent notifications enabled

---

## 📁 How To Use

### 1️⃣ Import Workflow

- Open n8n
- Import the provided JSON file

### 2️⃣ Configure Credentials

Add:
- Google Gemini (PaLM) API
- Google Sheets OAuth
- Telegram Bot Token

### 3️⃣ Activate Workflow

Turn workflow ON inside n8n.

### 4️⃣ Trigger

Send any message to your Telegram bot.

---

## 🎯 Use Case

This system is designed for:

- Traders
- Stock analysts
- Financial researchers
- News-based trading strategies
- Catalyst detection systems

---

## 📌 Key Advantages

- Fully automated
- Structured AI output
- Multi-source ingestion
- Real-time Telegram delivery
- Historical tracking in Sheets
- Scalable architecture

---

## 👤 Author

Bereket

---

## 📄 License

This project is for educational and research purposes.
