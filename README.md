# BidGuard AI 🛡️📑

> **AI-Powered Procurement Bid Compliance & Verification Platform (Smart India Hackathon)**

BidGuard AI automates public and private procurement tender compliance. It verifies bidder submissions, cross-references government registries (GST, PAN, UDYAM, EPFO), detects blacklisted vendors, evaluates technical and financial eligibility against tender requirements, and generates auditable compliance scores in real time.

---

## 🌟 Key Features

- **Automated Compliance Verification Engine**: Evaluates bidder documents and structured data against 13 core tender requirements (turnover, solvency, certifications, blacklisting, past experience).
- **Government Registry Cross-Verification**: Cross-verifies bidder identities and tax compliance against simulated and live government databases (GSTN, MCA/PAN, UDYAM, EPFO).
- **Multi-Role Portals**:
  - 👑 **Admin Portal**: System overview, vendor management, global verification audit logs, and bidder onboarding.
  - 📋 **Tender Authority Portal**: Tender creation, requirement definition, real-time analytics, and automated bid ranking.
  - 🏢 **Bidder Portal**: Bid submission, document status, requirement checklists, and discrepancy reviews.
- **Explainable Scoring & Audit Trails**: Generates transparent compliance percentages with granular evidence (PASS / FAIL / REVIEW / MISSING) per criteria.
- **RESTful API & Database Integration**: Built with FastAPI and powered by Supabase PostgreSQL with role-based policies.

---

## 🏗️ Architecture

```
bidguard-ai/
├── backend/
│   ├── engine/                     # Core compliance verification engine
│   │   ├── compliance_engine.py    # Main evaluation orchestrator
│   │   ├── requirement_checker.py  # Dotted-field logic & operator comparisons
│   │   ├── government_checker.py   # Registry lookup & blacklist screening
│   │   ├── cross_verification.py   # Identity consistency verification
│   │   └── scorer.py               # Compliance percentage & status aggregation
│   ├── data/                       # Mock government registries & tender datasets
│   ├── api_server.py               # FastAPI backend endpoints
│   ├── supabase_schema.sql         # Supabase database schema
│   └── requirements.txt            # Python dependencies
└── frontend/
    ├── src/                        # React UI with role-aware dashboards (Admin/Tender/Bidder)
    ├── package.json                # Dependencies & build scripts
    └── vite.config.ts              # Vite configuration
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Node.js 18+ & npm
- Supabase account (or local PostgreSQL)

---

### 1. Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

Create a `.env` file in `backend/`:
```env
SUPABASE_URL=your_supabase_project_url
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key
```

Execute `supabase_schema.sql` and `admin_frontend_migration.sql` in your Supabase SQL editor to initialize tables.

Start the API:
```bash
python api_server.py
# or: uvicorn api_server:app --reload --port 8000
```

---

### 2. Frontend Setup

```bash
cd ../frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

Open `http://localhost:5173` to access the portal.

---

## 🧪 Testing

Run automated compliance engine test suites:
```bash
cd backend
python -m unittest discover -s tests -v
```

---

## 🛠️ Tech Stack

- **Backend**: Python, FastAPI, Pydantic, Supabase-py
- **Frontend**: React 18, Vite, TypeScript, Tailwind CSS, Lucide Icons
- **Database / Auth**: Supabase (PostgreSQL), Row Level Security (RLS)
- **Data Engine**: Custom rule evaluation & fuzzy string matching verification

---

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
