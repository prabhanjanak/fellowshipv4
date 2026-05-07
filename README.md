# Sankara Academy of Vision - Fellowship Management System (v4)

A comprehensive, professional-grade platform designed for managing medical fellowship applications, entrance examinations, interview scheduling, and seat allocations at the Sankara Academy of Vision.

## 🚀 Project Overview

This system streamlines the entire lifecycle of a fellowship program—from the initial application by a candidate to the final seat allocation across various Sankara units and specialties. It is built with a focus on visual excellence, data integrity, and administrative efficiency.

### Key Features

*   **Intelligent Application Form**: A dynamic, multi-step application wizard with conditional visibility logic, real-time validation, and professional UI components (e.g., surgical experience tables, high-fidelity Indian phone inputs).
*   **Dynamic Form Builder**: Admins can configure form sections, fields, and instructions directly from the dashboard without touching code.
*   **Payment Infrastructure**: 
    *   Integrated **Razorpay** gateway for secure fee payments.
    *   Dynamic UPI QR code generation as a secondary/fallback payment method.
    *   Admin-configurable fee amounts per program.
*   **Role-Based Access Control (RBAC)**:
    *   **Super Admin**: Global configuration, user management, and system-wide overrides.
    *   **Program Admin**: Specific control over fellowship programs and application forms.
    *   **Central Exam Coordinator**: Manages the logistics of exams and interviews.
    *   **Display Operator**: Specialized role for managing live interview queue displays.
    *   **Candidate**: Restricted access to application status and exam portals.
*   **Seat Matrix Management**: Centralized management of available seats across units (e.g., Coimbatore, Bangalore, Guntur) and specialties (e.g., Cornea, Glaucoma, Vitreo-Retina).
*   **Interview & Exam Ecosystem**:
    *   Automated Exam assignments.
    *   Interview Panel creation and doctor assignments.
    *   Live **Panel Queue Management** with real-time status updates.
    *   Scoring interface for interviewers.
*   **Results & Rankings**: Automatic calculation of final scores based on weighted exam and interview results, generating rank-based allocation lists.
*   **Data Integration**: Bi-directional sync capabilities with Google Sheets for external reporting and data backup.

## 🛠 Tech Stack

### Frontend
*   **Framework**: React (with Vite)
*   **State Management**: TanStack Query (React Query)
*   **Styling**: Vanilla CSS + TailwindCSS (for utility-heavy components)
*   **Components**: Radix UI primitives, Lucide Icons, Framer Motion for premium animations.
*   **Features**: Dark/Light mode support, Responsive Design.

### Backend
*   **Environment**: Node.js with TypeScript
*   **Framework**: Express.js
*   **ORM**: Drizzle ORM (Type-safe SQL)
*   **Database**: PostgreSQL
*   **Security**: JWT-based authentication, password hashing (bcrypt), and middleware-level role protection.
*   **Storage**: Hybrid local/cloud object storage for candidate documents (LORs, photos).

## 📂 Project Structure

```text
├── artifacts/
│   ├── api-server/         # Node.js Express API (Backend)
│   ├── fellowship-exam/    # React/Vite Application (Frontend)
│   ├── db/                 # Shared Database Schemas and Migrations
│   └── ...                 # Exported data and scripts
├── deploy/                 # Deployment configurations and scripts
└── README.md               # You are here
```

## ⚙️ Setup & Installation

### Prerequisites
*   Node.js (v18+)
*   PostgreSQL (v14+)
*   pnpm (recommended)

### Database Setup
1. Create a database named `fellowship_db`.
2. Run the provided SQL migration scripts found in the `artifacts/fellowship_data_export.sql` or use the Drizzle push command.

### Local Development

**1. Backend:**
```bash
cd artifacts/api-server
pnpm install
# Configure .env with DATABASE_URL and RAZORPAY keys
pnpm run dev
```

**2. Frontend:**
```bash
cd artifacts/fellowship-exam
pnpm install
pnpm run dev
```

## 🚢 Deployment

The system is designed to be managed via **PM2**.

1. Build the frontend: `npm run build` in `fellowship-exam`.
2. Build the backend: `npm run build` in `api-server`.
3. Start processes:
   ```bash
   pm2 start dist/index.js --name fellowship-api
   ```

## 🔒 Environment Variables

Key variables required in `.env` files:
*   `DATABASE_URL`: PostgreSQL connection string.
*   `RAZORPAY_KEY_ID` / `RAZORPAY_KEY_SECRET`: For payment processing.
*   `JWT_SECRET`: For secure authentication.
*   `PRIVATE_OBJECT_DIR`: Local path for storing candidate uploads.

## 📄 License
Internal software for Sankara Academy of Vision. All rights reserved.