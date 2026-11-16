## Project Title:
AI Inventory and Sales Forecasting System

## Team information:

Team name: CSE4104-7B-T05 

Section: 7B

Team Leader Name: Nishan Sami

Team Leader ID: 11230321272

## Member List: 

1-Fahima Sultana Sakiya-11230321254

2-Avishek Banerjee Joy-11230321263

3-Nishan Sami-11230321272

4-Sathi Bayragi-11230321303

## Features:

- 🔐 Authentication with Owner and Staff roles
- 🛒 Product, category and supplier management
- 💰 Sales and purchase recording with automatic stock updates
- 📊 Dashboard with sales charts and low-stock alerts
- 📈 Demand forecasting (next 7 to 30 days)
- ⚠️ Stock-out risk and reorder recommendations
- 🤖 AI assistant for explanations and questions (OpenAI API)
- 📑 Sales reports (best-selling and slow-moving products)

## 🛠️ Technology Stack

| Layer | Technology |
|-------|------------|
| Frontend | React.js, Tailwind CSS, Recharts |
| Backend | Node.js, Express.js |
| Database | PostgreSQL |
| Forecasting | Python (pandas, Prophet / statsmodels) |
| AI | OpenAI API |
| Tools | GitHub, Postman, Draw.io, Vercel / Render |

**Stack:** PERN (PostgreSQL, Express, React, Node) + Python + OpenAI API

## 🏗️ System Architecture

```
React Frontend  ->  Node.js / Express API  ->  PostgreSQL
                          |
                          +->  Python Forecasting Service
                          +->  OpenAI API (AI advice and chat)
```

**Workflow:** Sales data → Forecast model → Risk and reorder calculation → AI explanation → Dashboard

## 📁 Repository Structure

```
ai-inventory-forecasting/
├── README.md
├── .gitignore
├── .env.example
├── docker-compose.yml                
│
├── docs/
│   ├── proposal/                     Project proposal
│   ├── srs/                          SRS document
│   ├── diagrams/                     Use case, ER, architecture diagrams
│   ├── api/                          API documentation / Postman collection
│   ├── team/                         Team information sheet, meeting notes
│   └── planning/                     Weekly plan and progress notes
│
├── frontend/                         React.js application
│   ├── public/
│   ├── src/
│   │   ├── assets/                   Images, icons
│   │   ├── components/               Reusable UI (Navbar, Table, Chart, Card)
│   │   ├── pages/                    Login, Dashboard, Products, Sales,
│   │   │                             Purchases, Forecast, Reports, AIChat, Users
│   │   ├── layouts/                  AuthLayout, MainLayout
│   │   ├── routes/                   Route config and protected routes
│   │   ├── context/                  Auth and app state
│   │   ├── hooks/                    Custom hooks
│   │   ├── services/                 API calls (axios) to the backend
│   │   ├── utils/                    Helpers and formatters
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   ├── tailwind.config.js
│   └── .env.example
│
├── backend/                          Node.js (Express) REST API
│   ├── src/
│   │   ├── config/                   DB connection, environment settings
│   │   ├── routes/                   auth, products, sales, purchases,
│   │   │                             suppliers, forecast, reports, ai, users
│   │   ├── controllers/              Request handling for each route
│   │   ├── services/                 Business logic (stock, sales, reports)
│   │   │   └── ai/                   aiService.js, prompts/ (OpenAI calls)
│   │   ├── models/                   Database queries / models
│   │   ├── middleware/               JWT auth, role check, validation, errors
│   │   ├── jobs/                     Scheduled nightly forecast job
│   │   ├── utils/                    Logger, response helpers
│   │   ├── app.js                    Express app setup
│   │   └── server.js                 Server entry point
│   ├── tests/                        API and unit tests
│   ├── package.json
│   └── .env.example
│
├── forecasting-service/              Python forecasting module
│   ├── app/
│   │   ├── main.py                   FastAPI entry point
│   │   ├── forecast.py               Moving average / Prophet models
│   │   ├── risk.py                   Days of stock left, risk, reorder quantity
│   │   ├── db.py                     Reads sales, saves forecasts
│   │   └── config.py
│   ├── scripts/
│   │   └── generate_demo_data.py     Creates synthetic sales data
│   ├── notebooks/                    Model experiments (optional)
│   ├── tests/
│   ├── requirements.txt
│   └── .env.example
│
├── database/
│   ├── schema.sql                    All CREATE TABLE statements
│   ├── seed.sql                      Demo categories, products, suppliers
│   ├── migrations/                   Versioned schema changes
│   └── er-diagram.png
│
└── .github/
    ├── workflows/ci.yml              Lint and tests on every push / PR
    └── pull_request_template.md
```

### Folder Overview

| Folder | Purpose |
|--------|---------|
| `frontend/` | React.js user interface: dashboard, forms, charts, AI chat |
| `backend/` | Express REST API: authentication, CRUD, stock logic, reports, AI calls |
| `forecasting-service/` | Python service for demand forecasting and stock-out risk |
| `database/` | PostgreSQL schema, seed data and migrations |
| `docs/` | Proposal, SRS, diagrams, API docs and planning notes |
| `.github/` | CI workflow and pull request template |

### How the Parts Connect

```
React Frontend  ->  Node.js / Express API  ->  PostgreSQL
                          |
                          +->  Python Forecasting Service
                          +->  OpenAI API (AI advice and chat)
```
## ABOUT PROJECT :

The AI Inventory and Sales Forecasting System is a web app that helps small shops manage their stock and sales more smartly. Many shops either overstock, which raises storage costs and causes wastage, or run out of popular items and lose customers. Our system uses AI to study past sales, predict future demand, track stock levels, and suggest how much to reorder. It is made for shop owners and staff of grocery stores, pharmacies, and small wholesalers, where owners use the dashboard for buying decisions and staff handle daily sales and stock entry. Unlike traditional systems that only record current stock and past sales, AI can spot sales patterns and forecast what will be needed next. Tools like Zoho Inventory, inFlow, and Odoo manage stock well but are costly, complex, and weak at demand prediction for tiny shops, while Oracle Supply Chain Planning is too expensive for them. Our project combines inventory management, AI sales forecasting, low stock alerts, and smart reorder advice in one simple platform.

