# 🛠️ Technical Implementation Plan

This document defines the technical implementation plan for FuelFlow MVP Phase 1.

The goal of this phase is to transform the completed documentation and database design into a working web application.

---

# 📖 Overview

FuelFlow MVP Phase 1 will be implemented as a responsive web application focused on manual fuel expense tracking.

The application will allow users to:

- Create an account
- Log in
- Register vehicles
- Register fuel refills
- View global fuel reports
- View estimated virtual tank data

---

# 🧱 Proposed Stack

## Frontend

| Technology | Purpose |
|---|---|
| React | Build the user interface |
| TypeScript | Add type safety to frontend code |
| Vite | Development and build tool |
| Tailwind CSS | UI styling |
| Recharts | Charts and data visualization |

---

## Backend

| Technology | Purpose |
|---|---|
| Node.js | Runtime environment |
| Express.js | REST API framework |
| TypeScript | Type-safe backend development |
| Prisma | ORM and database access |
| PostgreSQL | Relational database |

---

## Development Tools

| Tool | Purpose |
|---|---|
| Docker | Run services locally |
| GitHub | Version control |
| Markdown | Documentation |
| draw.io | Diagrams |
| IntelliJ IDEA | Main IDE for development | 
| Figma | UI/UX prototype | 
| Affinity Designer | Visual design and graphic assets | 

---

# 🏗️ System Architecture

FuelFlow will use a separated frontend and backend architecture.

```text
User
 ↓
React Frontend
 ↓
REST API Backend
 ↓
PostgreSQL Database
```

---

# 📁 Planned Project Structure

```text
fuelflow/
│
├── docs/
│   ├── 01-requirements.md
│   ├── 02-use-cases.md
│   ├── 03-activity-diagrams.md
│   ├── 04-database-design.md
│   └── 05-technical-implementation-plan.md
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── types/
│   │   └── utils/
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── middlewares/
│   │   └── utils/
│   │
│   ├── prisma/
│   │   └── schema.prisma
│   │
│   └── package.json
│
├── docker-compose.yml
└── README.md
```

---

# 🗄️ Database Implementation

The database will be based on the completed relational model.

Main tables:

- User
- Vehicle
- Gas
- Refill

The first database implementation step will be creating the Prisma schema.

---

# 🔌 Backend Modules

## Authentication Module

Responsible for:

- User registration
- Login
- Logout
- Password hashing
- Password recovery

---

## User Module

Responsible for:

- Viewing user profile
- Editing username
- Editing phone number
- Changing email
- Changing password

---

## Vehicle Module

Responsible for:

- Registering vehicles
- Editing vehicles
- Listing user vehicles
- Assigning fuel type to a vehicle

---

## Refill Module

Responsible for:

- Registering fuel refills
- Editing fuel refills
- Listing refill history
- Calculating refill cost

---

## Report Module

Responsible for:

- Global vehicle report
- Period-based report
- Fuel cost calculations
- Fuel efficiency calculations

---

## Virtual Tank Module

Responsible for:

- Estimated tank percentage
- Estimated remaining autonomy
- Historical km/L calculation

---

# 🔗 Initial API Endpoints

## Authentication

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/auth/register` | Register user |
| POST | `/api/auth/login` | Log in |
| POST | `/api/auth/logout` | Log out |
| POST | `/api/auth/recover-password` | Recover password |

---

## User

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/users/me` | Get current user profile |
| PUT | `/api/users/me` | Update user profile |
| PUT | `/api/users/me/email` | Change email |
| PUT | `/api/users/me/password` | Change password |

---

## Vehicles

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/vehicles` | List user vehicles |
| POST | `/api/vehicles` | Register vehicle |
| GET | `/api/vehicles/:id` | Get vehicle details |
| PUT | `/api/vehicles/:id` | Update vehicle |

---

## Gas

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/gas` | List fuel types |
| PUT | `/api/gas/:id` | Update fuel price |

---

## Refills

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/refills` | List refills |
| POST | `/api/refills` | Register refill |
| GET | `/api/refills/:id` | Get refill details |
| PUT | `/api/refills/:id` | Update refill |

---

## Reports

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/reports/vehicle/:id` | Get global vehicle report |
| GET | `/api/reports/vehicle/:id/period` | Get report by period |
| GET | `/api/reports/vehicle/:id/tank` | Get virtual tank data |

---

# 🖥️ Frontend Screens

## Public Screens

- Login page
- Register page
- Password recovery page

---

## Private Screens

- Dashboard
- Vehicle list
- Register vehicle form
- Edit vehicle form
- Register refill form
- Refill history
- Global report
- Virtual tank view
- User profile

---

# 🧩 Frontend Components

Suggested components:

```text
LoginForm
RegisterForm
VehicleCard
VehicleForm
RefillForm
RefillTable
ReportSummaryCard
VirtualTankCard
PeriodFilter
Navbar
Sidebar
```

---

# 🧮 Core Calculations

## Total paid

```text
total_paid = liters_refilled * price_per_liter
```

---

## Fuel efficiency

```text
km_per_liter = kilometers_traveled / liters_consumed
```

---

## Estimated autonomy

```text
estimated_autonomy = estimated_liters_available * average_km_per_liter
```

---

## Virtual tank percentage

```text
tank_percentage = estimated_liters_available / tank_capacity_liters * 100
```

---

# 🚦 Implementation Order

## Step 1 — Backend Setup

- Create backend project
- Configure TypeScript
- Configure Express
- Configure Prisma
- Configure PostgreSQL connection

---

## Step 2 — Database Schema

- Create Prisma models
- Run first migration
- Add seed data for fuel types

---

## Step 3 — Authentication

- Register user
- Login user
- Password hashing
- Basic protected routes

---

## Step 4 — Vehicles

- Create vehicle
- List vehicles
- Edit vehicle
- Connect vehicle with user and gas type

---

## Step 5 — Refills

- Create refill
- List refills
- Edit refill
- Store historical fuel price

---

## Step 6 — Reports

- Calculate global report
- Calculate period report
- Calculate virtual tank data

---

## Step 7 — Frontend Setup

- Create frontend project
- Configure Tailwind CSS
- Create layout
- Create routing structure

---

## Step 8 — Frontend Features

- Login/register pages
- Vehicle management
- Refill registration
- Dashboard
- Reports
- Virtual tank card

---

# ✅ MVP Completion Criteria

The MVP Phase 1 will be considered complete when the user can:

- Register an account
- Log in
- Register a vehicle
- Register fuel refills
- View refill history
- View a global vehicle report
- View estimated tank data
- Consult information by period

---

# 📚 Related Documentation

⬅️ Previous document: [Database Design Documentation](04-database-design.md)
