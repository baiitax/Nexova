# 🚀 Nexova Lead Engine

![Nexova Banner](https://via.placeholder.com/1200x300/0f172a/06b6d4?text=NEXOVA+LEAD+ENGINE)

> **Turning operational bottlenecks into automated revenue engines.**

Nexova Lead Engine is a proprietary, full-stack B2B SaaS platform designed to automate the two hardest parts of running a digital agency: finding highly qualified leads and executing personalized outreach at scale. 

The system autonomously scrapes high-ticket local businesses, identifies "invisible" digital leaks (missing websites, expired SSLs, lack of AI automation), and uses Google's Gemini API to draft context-aware sales pitches directly into a built-in CRM dashboard.

## ✨ Key Features

* **🕸️ Autonomous Lead Scraping:** A decoupled Node.js background engine that queries the Google Places API every 5 hours to find high-rated businesses with digital infrastructure gaps.
* **🧠 AI-Powered Outreach:** Native integration with the Google Gemini API to instantly generate personalized, high-converting cold emails based on the specific bottlenecks of the scraped lead.
* **📊 Modern CRM Dashboard:** A sleek, dark-mode Next.js interface to manage the sales pipeline, track outreach status, and schedule follow-ups.
* **⚡ Decoupled Architecture:** Heavy scraping jobs are isolated to a VPS background worker (preventing serverless timeouts), while the fast, edge-rendered dashboard is optimized for Vercel.

---

## 🛠️ Tech Stack

* **Frontend:** Next.js (App Router), React, Tailwind CSS, Framer Motion, Lucide React
* **Backend:** Next.js Route Handlers (API), Node.js (Background Cron Jobs)
* **Database & Auth:** Supabase (PostgreSQL), Prisma ORM
* **AI Integration:** Google Gemini API (`@google/genai`)
* **Scraping Engine:** Axios, Google Places API (New)

---

## 🏗️ System Architecture

1. **The Engine (VPS Worker):** A `node-cron` script runs every 5 hours. It fetches niche local businesses, filters for high ratings and missing web infrastructure, and pushes qualified leads to the Supabase database.
2. **The Database (Supabase):** PostgreSQL handles user authentication, stores structured lead data, and maintains an `OutreachLog` for follow-ups.
3. **The Dashboard (Next.js):** Pulls live data from Supabase. When a user clicks "Generate Draft," it passes the lead context to the Gemini API, which returns a ready-to-send, highly personalized email.

---

## 🚀 Getting Started

### Prerequisites
* Node.js 18.x or higher
* A Supabase account and project
* A Google Cloud Console account (for Places API & Gemini API keys)

### 1. Clone the repository
```bash
git clone [https://github.com/yourusername/nexova-lead-engine.git](https://github.com/baiitax/Nexova.git)
cd Nexova
