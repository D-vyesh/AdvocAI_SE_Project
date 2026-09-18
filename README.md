# ⚖️ AdvocAI

<div align="center">
  <p><strong>Next-Generation AI-Assisted Legal Tooling Platform</strong></p>
  <p>
    <img src="https://img.shields.io/badge/React-19-blue?logo=react" alt="React" />
    <img src="https://img.shields.io/badge/Vite-7-purple?logo=vite" alt="Vite" />
    <img src="https://img.shields.io/badge/Django-5.2-green?logo=django" alt="Django" />
    <img src="https://img.shields.io/badge/AI-LangChain-orange" alt="LangChain" />
    <img src="https://img.shields.io/badge/DB-PostgreSQL%20%7C%20MongoDB-blue" alt="Database" />
  </p>
</div>

---

## 🌟 Overview

**AdvocAI** is a comprehensive, modern web platform designed to revolutionize legal workflows. By integrating cutting-edge Artificial Intelligence with a highly polished, interactive user interface, it provides tools for document analysis, smart legal drafting, secure e-signatures, and lawyer collaboration.

The platform is split into a robust **Django REST Backend** powering the AI logic and background processing, and a dynamic **React + Vite Frontend** that delivers a premium, 3D-enhanced user experience.

---

## ✨ Key Features

- 🤖 **AI-Powered Legal Workflows**: Intelligent document summarization, legal document generation, and analysis powered by LangChain, Google Generative AI (Gemini), and OpenAI.
- ⚡ **Real-Time Collaboration & Chat**: WebSockets (via Django Channels) for real-time document interaction and AI chat assistance.
- 📝 **Rich Document Editor**: Advanced in-browser document editing and preview using TipTap, with support for Markdown and document export workflows.
- 🎨 **Premium UI/UX**: Highly polished frontend featuring Radix UI primitives, Tailwind CSS styling, and subtle 3D background elements powered by React Three Fiber and tsParticles.
- 🔐 **Secure & Scalable**: JWT-based authentication flow, with async task processing via Celery and Redis to handle heavy AI workloads seamlessly.

---

## 🏗️ Architecture & Tech Stack

### Frontend (User Interface)
- **Framework**: React 19, React Router 7, Vite 7
- **Styling**: Tailwind CSS 3, tailwind-merge, tailwindcss-animate
- **Components**: Radix UI, Lucide React (Icons)
- **Rich Text**: TipTap editor suite
- **Visuals**: Three.js, `@react-three/fiber`, `@react-three/drei`, `@tsparticles/react`
- **Networking**: Axios with centralized auth interceptors

### Backend (API & AI Core)
- **Framework**: Django 5.2, Django REST Framework 3.14
- **AI & NLP**: LangChain, Google Generative AI (Gemini), OpenAI
- **Async & Background Jobs**: Celery, Redis, Django Channels (Daphne)
- **Databases**: PostgreSQL (psycopg2), MongoDB (mongoengine/pymongo)
- **Document Processing**: PyMuPDF, python-docx, reportlab, xhtml2pdf
- **Auth**: djangorestframework-simplejwt, django-allauth, google-auth

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v18+ recommended)
- **Python** (3.10+ recommended)
- **Redis** server running (for Celery tasks and Channels)
- **PostgreSQL / MongoDB** instances

### 1. Backend Setup

```bash
cd backend

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirement.txt

# Setup environment variables (create a .env file)
# Example: 
# DATABASE_URL=postgres://user:pass@localhost/advocai
# REDIS_URL=redis://localhost:6379/0
# GOOGLE_API_KEY=your_gemini_key
# OPENAI_API_KEY=your_openai_key

# Run migrations
python manage.py migrate

# Start the development server (uses Daphne for ASGI/WebSockets)
python manage.py runserver
```

### 2. Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Setup environment variables
# Create frontend/.env containing:
# VITE_API_BASE_URL=http://localhost:8000/

# Start the development server
npm run dev
```

The frontend will be available at `http://localhost:5173`.

---

## 📂 Project Structure

```text
AdvocAI_SE_Project/
├── backend/                  # Django REST API & AI Workers
│   ├── ai_generator/         # AI models and core generation logic
│   ├── authentication/       # JWT and OAuth logic
│   ├── document_summarizer/  # PDF/Docx summarization endpoints
│   ├── legal_doc_generator/  # Legal template and drafting engine
│   └── documents/            # File storage and management
├── frontend/                 # React & Vite Application
│   ├── src/                  
│   │   ├── api/              # Axios configuration & interceptors
│   │   ├── Components/       # Reusable UI components & Modals
│   │   ├── context/          # Auth Context & State management
│   │   └── pages/            # Application views (Home, Dashboard, Chat)
│   └── public/               # Static assets
└── README.md
```

---

## 🛠️ Development & Contribution

- Ensure consistent code formatting.
- Frontend uses ESLint (`npm run lint`).
- Components should prefer Tailwind utility classes for styling.
- Backend background tasks (like heavy PDF generation or large AI prompts) must be deferred to Celery.

## 📄 License

*This project is unlicensed or under proprietary license. Please update accordingly.*
