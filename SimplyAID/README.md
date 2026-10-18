# 🏥 SimplyAID

**Industry-Grade First Aid & Workplace Safety Management System**

SimplyAID is a full-stack MERN application designed for industrial workplaces to manage first aid operations, track incidents, monitor inventory expiry, ensure compliance, and streamline employee health & safety workflows — all from a single platform.

---

## ✨ Features

### 🔐 Authentication & Roles
- Secure JWT-based authentication with bcrypt password hashing
- Role-based access control — **Doctor**, **Manager**, **Employee**, and more
- Guest browsing mode with action-gating for authenticated operations
- Google & Apple OAuth sign-in support

### 📊 Dashboards
- **Admin Dashboard** — Overview of incidents, inventory status, and key metrics
- **Manager Dashboard** — Team safety overview, department-level analytics, and employee management
- **Doctor Dashboard** — Treatment records, medical profiles, and clinical workflows

### 🚨 Incident Management
- Report workplace injuries with detailed forms (injured person, location, severity, body part mapping)
- Track incident lifecycle — from reporting through investigation to resolution
- Attach evidence/photos to incident reports
- Auto-generated unique incident IDs

### 💊 Inventory & First Aid Box Management
- Track first aid boxes across factory locations
- QR code generation for each box — scan to view contents and status
- Real-time stock level monitoring with low-stock alerts
- Box inspection workflows with compliance checklists

### ⏰ Expiry Tracking
- Automated expiry scheduler (runs every 24 hours)
- Color-coded expiry alerts (expired, expiring soon, safe)
- Dashboard view of all items approaching expiry

### ✅ Compliance & Inspections
- Compliance dashboard with regulatory checklist tracking
- Scheduled inspection forms for first aid boxes
- Audit log for all compliance-related actions

### 👥 Employee Management
- Comprehensive employee profiles (personal, organizational, medical, safety info)
- Auto-calculated profile completion percentage
- Employee ID card generation (downloadable as PDF)
- QR code per employee for quick identification
- Track first aid certifications and safety training status

### 🩺 Treatment Records
- Record and track workplace treatments
- Link treatments to incidents and employees
- Medical profile management with allergies, conditions, and medications

### 📈 Safety Analytics
- Visual charts and graphs powered by Recharts
- Incident trends, department comparisons, and severity breakdowns
- Exportable reports (PDF & CSV)

### 🔔 Notifications
- Real-time notification center
- Alerts for expiry, low stock, incident updates, and compliance deadlines

### 🤖 AI Assistant
- Built-in AI assistant for safety guidance and protocol queries

### 🌐 Internationalization
- Multi-language support (English & Hindi)

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 19, Vite 8, React Router 7 |
| **UI/Icons** | Lucide React, Custom CSS |
| **Charts** | Recharts |
| **Backend** | Node.js, Express 5 |
| **Database** | MongoDB with Mongoose 9 |
| **Auth** | JWT, bcryptjs, Google & Apple OAuth |
| **QR Codes** | qrcode library |
| **File Upload** | Multer |
| **Reports** | PDFKit, ExcelJS, json2csv |
| **Security** | Helmet, CORS |

---

## 📁 Project Structure

```
SimplyAID/
├── client/                    # React Frontend
│   ├── src/
│   │   ├── components/        # Reusable UI components
│   │   │   └── common/        # Navbar, Sidebar, AuthRequiredModal
│   │   ├── contexts/          # AuthContext, ScannerContext
│   │   ├── pages/             # All page components
│   │   ├── services/          # API service layer (Axios)
│   │   ├── utils/             # Translations & helpers
│   │   ├── App.jsx            # Root component with routing
│   │   └── main.jsx           # Entry point
│   ├── index.html
│   ├── vite.config.js
│   └── package.json
│
├── server/                    # Express Backend
│   ├── config/                # Database connection
│   ├── controllers/           # Route handlers (17 controllers)
│   ├── middleware/             # Auth & error handling middleware
│   ├── models/                # Mongoose schemas (14 models)
│   ├── routes/                # API route definitions (18 route files)
│   ├── seeds/                 # Database seeders
│   ├── uploads/               # File upload directory
│   ├── utils/                 # Helpers (QR, notifications, expiry scheduler)
│   ├── server.js              # Entry point
│   └── package.json
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** v18 or higher
- **MongoDB** running locally or a MongoDB Atlas connection string
- **npm** (comes with Node.js)

### 1. Clone the Repository

```bash
git clone https://github.com/Dhruv-code91/Simply_AID.git
cd Simply_AID/SimplyAID
```

### 2. Setup the Backend

```bash
cd server
npm install
```

Create a `.env` file in the `server/` directory:

```env
PORT=5000
NODE_ENV=development
MONGO_URI=mongodb://localhost:27017/simplyaid
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRE=7d
CLIENT_URL=http://localhost:5173
```

Start the server:

```bash
npm run dev
```

> ✅ You should see: `🚀 SimplyAID Server running on port 5000` and `✅ MongoDB Connected`

### 3. Setup the Frontend

Open a **new terminal**:

```bash
cd client
npm install
npm run dev
```

> ✅ You should see: `VITE ready` with `Local: http://localhost:5173/`

### 4. Open in Browser

Navigate to **http://localhost:5173/**

### 5. Seed Sample Data (Optional)

```bash
cd server
npm run seed
```

---

## 📜 API Endpoints

| Category | Base Route | Description |
|---|---|---|
| Auth | `/api/auth` | Login, Register, OAuth |
| Users | `/api/users` | User CRUD operations |
| Companies | `/api/companies` | Company management |
| Departments | `/api/departments` | Department CRUD |
| Employees | `/api/employees` | Employee profiles & ID cards |
| Incidents | `/api/incidents` | Incident reporting & tracking |
| Inventory | `/api/inventory` | First aid box & stock management |
| Treatments | `/api/treatments` | Treatment record management |
| Medical Profiles | `/api/medical-profiles` | Employee medical data |
| Inspections | `/api/inspections` | Box inspection workflows |
| Compliance | `/api/compliance` | Compliance checks & status |
| Expiry | `/api/expiry` | Expiry alerts & schedules |
| Analytics | `/api/analytics` | Safety analytics & statistics |
| Reports | `/api/reports` | PDF & CSV report generation |
| Notifications | `/api/notifications` | Notification management |
| Scanners | `/api/scanners` | QR scanner device management |
| Audit Logs | `/api/audit-logs` | System audit trail |
| Health | `/api/health` | Server health check |

---

## 🔑 User Roles

| Role | Access Level |
|---|---|
| **Doctor** | Full access — inventory, treatments, compliance, analytics, inspections, AI assistant |
| **Manager** | Manager dashboard, employees, reports, scan history |
| **Employee** | View incidents, profile, QR scan, notifications |
| **Guest** | Browse incidents dashboard (read-only) |

---

## 📋 Available Scripts

### Server (`server/`)

| Command | Description |
|---|---|
| `npm run dev` | Start with nodemon (auto-restart) |
| `npm start` | Start in production mode |
| `npm run seed` | Seed database with sample data |

### Client (`client/`)

| Command | Description |
|---|---|
| `npm run dev` | Start Vite dev server |
| `npm run build` | Create production build |
| `npm run preview` | Preview production build |

---
