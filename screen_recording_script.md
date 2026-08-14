# 🎬 ValueScout AI — Screen Recording Voiceover Script

**Duration:** 2–4 Minutes  
**Tone:** Formal, Professional, Technical Demo  
**Speaker:** Project Creator / Developer  

---

## 🎙️ INTRO — Title Card (0:00 – 0:15)

> *[Show a title card or the browser tab with the ValueScout AI homepage loading]*

**VOICEOVER:**

"Hello and welcome. My name is Sanju L., and today I'll be walking you through **ValueScout AI** — an AI-powered, cross-platform e-commerce price comparison and analytics engine that I have built from the ground up. This system uses real-time web scraping, Google's Gemini 3.6 Flash AI model, and a Python FastAPI backend to help consumers detect the best product deals across Indian marketplaces — and even identify deceptive pricing tactics."

---

## 🖥️ SECTION 1 — Homepage & UI Walkthrough (0:15 – 0:55)

> *[Show the full homepage: header, search bar, FILTERS button, footer]*

**VOICEOVER:**

"Here is the landing page of ValueScout AI. The interface follows a **neo-futuristic dark theme** with glassmorphism card effects, custom typography from Google Fonts, and subtle floating animations. At the top, you can see the branding and a live status indicator confirming the Neural Engine is online."

> *[Hover over the search bar]*

"The core interaction begins with this search bar. A user can type any product — for example, *'Samsung Galaxy S24 Ultra'* or *'iPhone 15 128GB'* — and click **Initialize Scan** to trigger a full cross-platform comparison."

> *[Click the FILTERS button to open the Advanced Filters drawer]*

"Before initiating the scan, users also have access to an **Advanced Custom Filters** panel. This drawer provides six distinct control parameters."

> *[Scroll through the filters slowly]*

"These include: **Price Range** — where users can set a minimum and maximum budget in Indian Rupees; **Item Condition** — to filter by New, Used, or Refurbished listings; **Delivery Time and Cost** — to prioritize free or express delivery options; **Minimum Rating** — to enforce a quality threshold of 3.5, 4.0, or 4.5 stars; **Target Platform** — allowing users to focus on a specific marketplace such as Amazon, Flipkart, Croma, or OLX; and finally **Sort Listings By** — which supports sorting by AI-optimized best value, price ascending, price descending, or highest rating."

"These filters operate in a **dual-engine architecture** — they are sent to the backend AI model to influence the Gemini prompt, and they also apply instantly on the client side for real-time re-filtering of existing results."

---

## 🔍 SECTION 2 — Live Product Scan & Results (0:55 – 1:45)

> *[Type a product name like "iPhone 15 128GB" and click INITIALIZE SCAN]*

**VOICEOVER:**

"Let me now demonstrate a live product scan. I'll search for *'iPhone 15 128GB'*."

> *[Show the loader animation spinning]*

"The system is now performing multiple operations in sequence: first, it queries SerpAPI's Google Shopping engine for real-time marketplace listings across India. It then applies a **diverse platform filter** to ensure representation from multiple e-commerce sources — not just one dominant platform. These listings are then sent to **Google Gemini 3.6 Flash** with a detailed analytical prompt."

> *[Results appear — show the Winner Dashboard]*

"Here are the results. The **Optimal Value Deal** card highlights the single best product across all platforms. You can see the winning product title, its live price displayed prominently in cyan, along with key specifications: the platform, condition, star rating, warranty period, and delivery information."

> *[Scroll to the AI Verdict section]*

"Below that, the **AI Verdict** section provides a two-sentence natural language explanation of why this particular listing was selected over the alternatives."

> *[Show the Deceptive Pricing Banner if visible]*

"If the AI detects deceptive pricing — where a seller artificially inflates the price in a prior month to make the current deal appear more attractive — a red **warning banner** is displayed with a detailed explanation of the price manipulation."

> *[Scroll to the Price Trajectory Chart]*

"This **6-Month Price Trajectory Chart**, rendered using Chart.js, visualizes the product's price movement from March 2026 to August 2026. You can clearly see the artificial price spike in July, confirming the fake discount pattern."

> *[Scroll to the Comparison Matrix Table]*

"Finally, the **Cross-Platform Comparison Matrix** displays all analyzed marketplace listings in a structured table — showing each platform's price, condition, rating, warranty, and delivery terms side by side."

---

## 📄 SECTION 3 — PDF Report Generation (1:45 – 2:15)

> *[Click the REPORT button in the winner card header]*

**VOICEOVER:**

"ValueScout AI also includes a **PDF report export** feature. By clicking the Report button, the system generates a high-resolution, colorful PDF document."

> *[Show the button changing to "Generating PDF..." then the download completing]*

"The PDF is rendered using **html2canvas** and **jsPDF**. It captures a dedicated off-screen template that mirrors the entire analysis — including the brand header, winner card, AI verdict, deceptive pricing warning, the price trajectory chart as a high-DPI image, and the full comparison matrix table."

> *[Open the downloaded PDF file briefly]*

"As you can see, the exported report maintains the vibrant dark-theme design with neon cyan and emerald accents — making it suitable for sharing or archival purposes."

---

## ⚙️ SECTION 4 — Terminal & Backend Explanation (2:15 – 3:15)

> *[Switch to the terminal / VS Code terminal showing the FastAPI server]*

**VOICEOVER:**

"Now let me walk you through the backend architecture. The server is built with **Python FastAPI** and is launched using **Uvicorn**."

> *[Show the terminal command: `uvicorn main:app --reload`]*

"Here I run the command `uvicorn main:app --reload`, which starts the development server on port 8000 with hot-reloading enabled."

> *[Show the terminal output with the emoji logs]*

"In the terminal, you can observe the server's real-time logging. When a request arrives, the system prints a **search query log** with the active filter parameters. It then checks the **Supabase** database cache — if an identical unfiltered query was previously analyzed, the cached result is returned instantly, avoiding redundant API calls."

"If no cache exists, the system fetches listings from **SerpAPI**, applies the diverse platform prioritization algorithm, constructs a detailed AI prompt with user filter constraints, and sends it to **Google Gemini 3.6 Flash** with a JSON response schema."

> *[Show the main.py file briefly — highlight the analyze_product function signature]*

"The `/analyze` endpoint accepts the query string along with six optional filter parameters: `min_price`, `max_price`, `condition`, `delivery`, `min_rating`, and `sort_by`. These parameters are injected directly into the Gemini prompt to influence the AI's selection logic."

> *[Show the requirements.txt or .env file briefly]*

"The project dependencies include **FastAPI**, **Uvicorn**, **Requests** for HTTP calls, **google-genai** for the Gemini AI client, and **Supabase** for the PostgreSQL-backed caching layer. API keys for SerpAPI, Gemini, and Supabase are securely stored in a `.env` environment file."

---

## 🏁 SECTION 5 — Closing & Tech Stack Summary (3:15 – 3:45)

> *[Return to the browser showing the ValueScout AI homepage]*

**VOICEOVER:**

"To summarize the technology stack: the **frontend** is built with pure HTML, CSS, and vanilla JavaScript — featuring glassmorphism design, Chart.js for data visualization, and html2canvas with jsPDF for PDF export. The **backend** is powered by Python FastAPI with Google Gemini 3.6 Flash AI, SerpAPI for real-time product data, and Supabase for intelligent caching."

"ValueScout AI demonstrates a complete, production-grade AI application — from real-time data ingestion and neural analysis to interactive visualization and exportable intelligence reports."

"Thank you for watching."

---

## 📋 RECORDING CHECKLIST

Use this checklist while recording to make sure you hit every beat:

| # | Scene | Duration | Action |
|---|-------|----------|--------|
| 1 | Title card / Homepage load | 15s | Show landing page |
| 2 | Search bar + FILTERS drawer | 40s | Open filters, explain each one |
| 3 | Live product scan | 50s | Search, show loader, results, chart, table |
| 4 | PDF report download | 30s | Click Report, show PDF |
| 5 | Terminal + backend walkthrough | 60s | Show server, logs, code, .env |
| 6 | Closing summary | 30s | Return to UI, summarize stack |

**Total: ~3 min 45 sec**
