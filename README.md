# Sankara Academy of Vision – Fellowship Management System (v4)

A comprehensive, enterprise-grade platform designed to manage the complete fellowship lifecycle at Sankara Academy of Vision — from candidate registration and application submission to entrance examinations, interview coordination, ranking, and final seat allocation.

The platform is built with a strong focus on:

* Administrative efficiency
* Professional candidate experience
* Secure data handling
* Real-time workflow management
* Scalable multi-campus operations

---

# 🌟 Highlights

## End-to-End Fellowship Workflow

The system digitizes and automates the entire admission pipeline:

1. Fellowship application submission
2. Document uploads and verification
3. Application fee payment
4. Entrance examination management
5. Interview scheduling and panel assignment
6. Real-time interview queue handling
7. Scoring and ranking
8. Seat allocation across Sankara units and specialties

---

# 🖥 Product Showcase

## Candidate Application Portal

The platform provides a modern multi-step application wizard with:

* Dynamic form sections
* Conditional field visibility
* Real-time validation
* Professional UI/UX
* Mobile responsive layout
* Secure document upload support
* Guided application flow

### Includes:

* Personal information collection
* Academic qualifications
* Fellowship preferences
* Surgical experience matrix
* Publications and presentations
* Statement of purpose
* Document uploads
* Payment integration

---

## Payment Infrastructure

Integrated payment ecosystem with:

* Razorpay payment gateway
* Dynamic UPI QR code generation
* Online payment verification
* Payment success acknowledgement
* Transaction tracking
* Admin-configurable fee structure

---

## Admin Dashboard

A centralized administrative console for managing:

* Applications
* Fellowship programs
* Interview panels
* Seat matrix
* Exam coordination
* Candidate rankings
* Allocation workflows
* Reports and exports

The dashboard is designed for high-volume operational efficiency with:

* Fast filtering
* Search capabilities
* Real-time updates
* Role-based controls
* Responsive layouts

---

## Interview & Examination Ecosystem

Advanced tools for conducting and managing fellowship evaluations:

### Features

* Automated exam assignments
* Interview panel creation
* Doctor allocation to panels
* Real-time candidate queue management
* Live display operator support
* Interview scoring interface
* Weighted score calculations
* Rank list generation

---

## Seat Matrix Management

Centralized management of seats across:

### Sankara Units

* Coimbatore
* Bangalore
* Guntur
* Other participating centers

### Fellowship Specialties

* Cornea
* Glaucoma
* Vitreo Retina
* Cataract
* Pediatric Ophthalmology
* Oculoplasty
* Additional specialties

Supports:

* Seat availability tracking
* Program-wise allocation
* Category-based seat handling
* Allocation status management

---

# 🔐 Role-Based Access Control (RBAC)

The platform implements granular permission-based access.

## Roles

### Super Admin

* Global configuration access
* User and role management
* System-wide overrides
* Complete operational visibility

### Program Admin

* Program-specific administration
* Form management
* Candidate review
* Interview coordination

### Central Exam Coordinator

* Examination logistics
* Candidate scheduling
* Hall management
* Evaluation coordination

### Display Operator

* Live queue display management
* Interview flow coordination
* Candidate status updates

### Candidate

* Application submission
* Payment handling
* Status tracking
* Exam and interview access

---

# 🧠 Dynamic Form Builder

A configurable no-code form builder allowing administrators to:

* Create sections dynamically
* Add custom fields
* Configure validation rules
* Enable conditional visibility
* Modify instructions
* Reorder fields
* Configure mandatory/optional logic

No code changes required.

---

# 🔄 Data Integration

Supports bi-directional synchronization with:

* Google Sheets
* External reporting workflows
* Data backup pipelines
* Export/import utilities

---

# ⚡ Tech Stack

# Frontend

| Technology     | Purpose                         |
| -------------- | ------------------------------- |
| React + Vite   | Frontend framework              |
| TypeScript     | Type-safe development           |
| TailwindCSS    | Utility-first styling           |
| Vanilla CSS    | Custom design system            |
| TanStack Query | API state management            |
| Radix UI       | Accessible component primitives |
| Framer Motion  | Premium animations              |
| Lucide Icons   | Icon system                     |

## Frontend Features

* Dark/Light mode
* Responsive layouts
* High-performance rendering
* Animated transitions
* Modern dashboard experience
* Accessible UI patterns

---

# Backend

| Technology  | Purpose             |
| ----------- | ------------------- |
| Node.js     | Runtime environment |
| Express.js  | API framework       |
| TypeScript  | Backend type safety |
| PostgreSQL  | Relational database |
| Drizzle ORM | Type-safe ORM       |
| JWT         | Authentication      |
| bcrypt      | Password hashing    |

## Backend Features

* Secure authentication
* Role-based middleware
* RESTful APIs
* Transaction-safe operations
* Modular architecture
* Scalable deployment design

---

# 📂 Project Structure

```bash
├── artifacts/
│   ├── api-server/         # Express + TypeScript Backend
│   ├── fellowship-exam/    # React/Vite Frontend
│   ├── db/                 # Shared schemas and migrations
│   ├── exports/            # Generated reports and backups
│   └── scripts/            # Utility scripts
│
├── deploy/                 # Deployment configurations
├── docs/                   # Documentation assets
├── screenshots/            # Application screenshots
└── README.md
```

---

# ⚙️ Setup & Installation

## Prerequisites

Ensure the following are installed:

* Node.js v18+
* PostgreSQL v14+
* pnpm (recommended)
* PM2 (for production deployment)

---

# 🗄 Database Setup

Create a PostgreSQL database:

```sql
CREATE DATABASE fellowship_db;
```

Run migrations using:

```bash
pnpm drizzle-kit push
```

Or import the provided SQL dump:

```bash
psql -U postgres -d fellowship_db -f artifacts/fellowship_data_export.sql
```

---

# 🚀 Local Development

## 1. Backend Setup

```bash
cd artifacts/api-server
pnpm install
```

Create `.env` file:

```env
DATABASE_URL=postgresql://username:password@localhost:5432/fellowship_db
JWT_SECRET=your_secret
RAZORPAY_KEY_ID=your_key
RAZORPAY_KEY_SECRET=your_secret
PRIVATE_OBJECT_DIR=./uploads
```

Run development server:

```bash
pnpm run dev
```

---

## 2. Frontend Setup

```bash
cd artifacts/fellowship-exam
pnpm install
pnpm run dev
```

Frontend will typically run on:

```bash
http://localhost:5173
```

---

# 🚢 Production Deployment

The application is designed for PM2-based deployments.

## Build Frontend

```bash
cd artifacts/fellowship-exam
pnpm run build
```

## Build Backend

```bash
cd artifacts/api-server
pnpm run build
```

## Start Backend with PM2

```bash
pm2 start dist/index.js --name fellowship-api
```

---

# 🔒 Environment Variables

## Required Backend Variables

| Variable            | Description                   |
| ------------------- | ----------------------------- |
| DATABASE_URL        | PostgreSQL connection string  |
| JWT_SECRET          | Authentication secret         |
| RAZORPAY_KEY_ID     | Razorpay public key           |
| RAZORPAY_KEY_SECRET | Razorpay secret key           |
| PRIVATE_OBJECT_DIR  | Candidate upload storage path |

---

# 📸 Suggested Screenshot Organization

Create a folder:

```bash
/screenshots
```

Recommended screenshot names:

```bash
candidate-application-step-1.png
candidate-education-section.png
surgical-experience-matrix.png
document-upload.png
payment-success.png
admin-dashboard.png
interview-panel-management.png
live-queue-management.png
seat-matrix.png
ranking-dashboard.png
```

Then reference them inside README like:

```md
## Candidate Application Portal
![Application Form](./screenshots/candidate-application-step-1.png)

## Admin Dashboard
![Dashboard](./screenshots/admin-dashboard.png)
```

---

# 🧩 Core Functional Modules

| Module               | Description                           |
| -------------------- | ------------------------------------- |
| Application System   | Candidate registration and submission |
| Form Builder         | Dynamic configurable forms            |
| Payments             | Razorpay + UPI integration            |
| Document Management  | Candidate uploads and storage         |
| Exam Management      | Entrance examination handling         |
| Interview Management | Panel and scheduling workflows        |
| Queue System         | Real-time display operations          |
| Rankings Engine      | Weighted score computation            |
| Seat Allocation      | Multi-unit allocation engine          |
| Reports & Exports    | Administrative analytics              |

---

# 🎯 Design Philosophy

The platform focuses on:

* Operational reliability
* Clinical-grade workflow precision
* Administrative simplicity
* Premium user experience
* Scalability for future fellowship cycles
* Strong data integrity and security

---

# 📈 Future Expansion Possibilities

Potential enhancements:

* Email/SMS notifications
* Candidate analytics dashboard
* AI-assisted screening
* Online examination proctoring
* Multi-language support
* Advanced reporting engine
* Audit trails and compliance logs

---

# 📄 License

Internal proprietary software developed for Sankara Academy of Vision.

All rights reserved.

---

# 🤝 Acknowledgements

Developed to support and streamline the fellowship admission ecosystem at Sankara Academy of Vision through modern, scalable, and efficient digital infrastructure.
