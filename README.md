# 💰 Finance SaaS – Financial Management Platform

Finance SaaS is a modern, comprehensive financial management platform designed to help individuals and businesses take control of their finances. Built with cutting-edge technologies like **Next.js 14 (App Router)**, **Hono.js**, **Drizzle ORM**, and **Clerk**, it offers a robust and scalable solution for tracking accounts, categories, and transactions.

Whether you're managing personal expenses or business ledgers, Finance SaaS provides intuitive tools for efficient financial organization and insights.

---

## ✨ Features

- 🔐 **Secure User Authentication** – Powered by Clerk for seamless and secure sign-up/sign-in flows.
- 🏦 **Account Management** – Create, view, update, and delete multiple financial accounts (e.g., Checking, Savings).
- 📂 **Category Organization** – Define custom categories (e.g., Food, Rent, Salary) to classify your income and expenses.
- 💸 **Transaction Tracking** – Log detailed transactions and associate them with accounts and categories.
- ⚡ **Robust API Endpoints** – Built with Hono.js for fast and efficient data interactions.
- 🧠 **Modern ORM & DB** – Drizzle ORM with Neon PostgreSQL ensures power and scalability.
- 🚀 **Optimized Rendering** – Powered by Next.js 14 App Router for blazing-fast performance.

---

## 🛠️ Tech Stack

| Tool           | Purpose                      |
|----------------|------------------------------|
| **Next.js 14** | App Router frontend framework |
| **Hono.js**    | Lightning-fast API routes     |
| **Drizzle ORM**| Type-safe DB access layer     |
| **Neon**       | Scalable PostgreSQL database  |
| **Clerk**      | Authentication provider       |
| **Zod**        | Input validation              |
| **date-fns**   | Date utilities                |
| **CUID2**      | Unique IDs                    |
| **Vercel**     | Deployment                    |

---

## ⚙️ Getting Started

### Prerequisites

- Node.js v18+
- pnpm, npm, yarn, or bun
- Clerk account
- Neon account (or any PostgreSQL database)
- [ngrok](https://ngrok.com/) (for local webhook testing)

---

## 🧑‍💻 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/DanielAvishid/finance-sass.git
cd finance-sass
```

### 2. Install Dependencies

Use your preferred package manager to install project dependencies:

```bash
pnpm install
# or
npm install
# or
yarn install
# or
bun install
```

### 3. Set Up Environment Variables

Create a .env.local file in the root of the project:

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_YOUR_CLERK_PUBLISHABLE_KEY
CLERK_SECRET_KEY=sk_test_YOUR_CLERK_SECRET_KEY

DATABASE_URL="postgresql://[user]:[password]@[host]:[port]/[database]"
# Example for Neon:
# DATABASE_URL="postgresql://user:password@ep-random-name-12345.us-east-2.aws.neon.tech/database-name?sslmode=require"
```

🔑 Clerk Keys: Get these from your Clerk Dashboard.
🛢️ DATABASE_URL: Get this from your Neon project or another PostgreSQL provider.

## 🗃️ Database Setup

### Push Schema to Database

```bash
pnpm drizzle-kit push
```

This syncs your Drizzle schema to the connected database.

## 🧪 Running Locally

### Start the Development Server

```bash
pnpm dev
# or
npm run dev
# or
yarn dev
# or
bun dev
```
Open your browser at http://localhost:3000

## 📡 API Endpoints (Hono.js)

API routes are built with [Hono.js](https://hono.dev), mounted inside the Next.js App Router.

| Method | Route                        | Description                                              |
|--------|------------------------------|----------------------------------------------------------|
| GET    | `/api/accounts`              | Get all accounts for the authenticated user              |
| GET    | `/api/accounts/:id`          | Get a specific account by ID                             |
| POST   | `/api/accounts`              | Create a new account                                     |
| POST   | `/api/accounts/bulk-delete`  | Delete multiple accounts by IDs                          |
| PATCH  | `/api/accounts/:id`          | Update an existing account                               |
| DELETE | `/api/accounts/:id`          | Delete an account                                        |

