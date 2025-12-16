<p align="center">
  <img src="https://img.shields.io/badge/N--ATLaS-AI%20Powered-FF6B6B?style=for-the-badge" alt="N-ATLaS"/>
  <img src="https://img.shields.io/badge/Languages-English%20%7C%20Hausa%20%7C%20Igbo%20%7C%20Yoruba-4A90A4?style=for-the-badge" alt="Languages"/>
  <img src="https://img.shields.io/badge/Awarri-Developer%20Challenge%202025-gold?style=for-the-badge" alt="Awarri"/>
</p>

<h1 align="center">🏥 Kliniq</h1>

<p align="center">
  <strong>AI-Powered Multilingual Healthcare Platform for Nigeria</strong>
</p>

<p align="center">
  <em>Breaking language barriers in healthcare through intelligent AI triage, voice-enabled consultations, and seamless patient-clinician communication in English, Hausa, Igbo, and Yoruba.</em>
</p>

<p align="center">
  <a href="#demo">View Demo</a> •
  <a href="#problem">The Problem</a> •
  <a href="#solution">Our Solution</a> •
  <a href="#repositories">Repositories</a> •
  <a href="#quick-start">Quick Start</a>
</p>

---

## 🎥 Demo

> *Add demo video link or screenshots here*

---

<a id="problem"></a>
## 🌍 The Problem

In Nigeria, **over 60% of the population** speaks indigenous languages as their primary language, yet healthcare systems operate predominantly in English. This creates critical barriers that cost lives:

| Challenge | Impact |
|-----------|--------|
| 🚫 **Language Barrier** | Patients can't accurately describe symptoms |
| ⏰ **Delayed Care** | Miscommunication leads to misdiagnosis |
| 🏥 **Access Inequality** | Rural and elderly populations excluded |
| 📝 **Information Gap** | Medical records incomprehensible to patients |
| 👩‍⚕️ **Clinician Overload** | Routine queries overwhelm healthcare workers |

---

<a id="solution"></a>
## 💡 Our Solution

**Kliniq** is a comprehensive healthcare platform powered by **N-ATLaS** (Nigerian-Adapted Translation and Language System) — our custom multilingual AI model fine-tuned for Nigerian languages and medical terminology.

### 🧠 N-ATLaS: The AI Engine

Our custom LLM understands and responds in:
- 🇬🇧 **English**
- 🇳🇬 **Hausa** (spoken by 70M+ Nigerians)
- 🇳🇬 **Igbo** (spoken by 45M+ Nigerians)  
- 🇳🇬 **Yoruba** (spoken by 45M+ Nigerians)

### ✨ Key Features

<table>
<tr>
<td width="50%">

**👤 For Patients**
- 💬 AI health assistant in your language
- 🎙️ Voice-first interface with transcription
- 🏥 Link to multiple hospitals via codes
- 📅 Book and manage appointments
- 📊 Track health vitals and history

</td>
<td width="50%">

**👩‍⚕️ For Clinicians**
- 📊 Smart dashboard with AI triage
- 👥 Patient management with full history
- 🔍 AI-powered patient analysis
- ✅ Appointment approval workflow
- 🏆 Gamification for engagement

</td>
</tr>
</table>

---

<a id="repositories"></a>
## 📦 Repositories

This project consists of two repositories:

| Repository | Description | Tech Stack |
|------------|-------------|------------|
| **[Kliniq Frontend](https://github.com/Twilight-Techy/kliniq-ui)** | Next.js web application with patient and clinician dashboards | Next.js 16, React 19, TypeScript, Tailwind CSS 4 |
| **[Kliniq API](https://github.com/Twilight-Techy/kliniq-api)** | FastAPI backend with N-ATLaS AI integration | FastAPI, PostgreSQL, SQLAlchemy, Modal |

---

<a id="quick-start"></a>
## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Python 3.11+
- PostgreSQL 15+

### 1. Clone Both Repositories

```bash
# Clone frontend
git clone https://github.com/Twilight-Techy/kliniq-ui.git

# Clone backend
git clone https://github.com/Twilight-Techy/kliniq-api.git
```

### 2. Setup Backend

```bash
cd kliniq-api

# Create virtual environment
python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # macOS/Linux

# Install dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Edit .env with your database credentials

# Run migrations
alembic upgrade head

# Seed test data
python -m scripts.seed_test_data

# Start server
uvicorn src.main:app --reload --port 8001
```

### 3. Setup Frontend

```bash
cd kliniq-ui

# Install dependencies
npm install

# Configure environment
echo "NEXT_PUBLIC_API_URL=http://localhost:8001" > .env

# Start development server
npm run dev
```

### 4. Access the Application

- **Frontend**: [http://localhost:3000](http://localhost:3000)
- **API Docs**: [http://localhost:8001/docs](http://localhost:8001/docs)

---

## 🔑 Demo Accounts

| Role | Email | Password |
|------|-------|----------|
| 👤 Patient | `dayo@test.com` | `Test1234!` |
| 👩‍⚕️ Nurse | `ngozi@test.com` | `Test1234!` |
| 👨‍⚕️ Doctor | `emeka@test.com` | `Test1234!` |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         USER INTERFACES                          │
│  ┌──────────────────────┐    ┌─────────────────────────────────┐ │
│  │   Patient Dashboard  │    │      Clinician Dashboard        │ │
│  │   • AI Chat          │    │      • Nurse Portal             │ │
│  │   • Appointments     │    │      • Doctor Portal            │ │
│  │   • Health Records   │    │      • Patient Management       │ │
│  └──────────────────────┘    └─────────────────────────────────┘ │
└───────────────────────────────┬─────────────────────────────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                        KLINIQ API (FastAPI)                      │
│  ┌─────────────┐  ┌──────────────┐  ┌────────────────────────┐  │
│  │    Auth     │  │   Dashboard  │  │      Clinician         │  │
│  │   Module    │  │    Module    │  │       Module           │  │
│  └─────────────┘  └──────────────┘  └────────────────────────┘  │
│                            │                                     │
│                            ▼                                     │
│              ┌─────────────────────────────┐                     │
│              │      N-ATLaS LLM Service    │                     │
│              │  • Multilingual Chat        │                     │
│              │  • Symptom Triage           │                     │
│              │  • Tool Calling (Actions)   │                     │
│              └─────────────┬───────────────┘                     │
└────────────────────────────┼────────────────────────────────────┘
                             │
                             ▼
              ┌─────────────────────────────┐
              │      Modal Cloud GPU        │
              │   (N-ATLaS Model Hosting)   │
              └─────────────────────────────┘
```

---

## 🏆 Awarri Developer Challenge 2025

This project was built for the **Awarri Developer Challenge 2025** demonstrating:

| Criteria | How We Address It |
|----------|-------------------|
| **Social Impact** | Breaking language barriers in Nigerian healthcare |
| **Technical Innovation** | Custom N-ATLaS multilingual AI model |
| **User Experience** | Beautiful, accessible, voice-first design |
| **Scalability** | Enterprise-ready architecture with Modal cloud AI |
| **Real-World Applicability** | Solving actual clinical workflow challenges |

---

## 👨‍💻 Team

> *Add team member information here*

---

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

<p align="center">
  <strong>Built with ❤️ for Nigerian Healthcare</strong>
</p>

<p align="center">
  <sub>Awarri Developer Challenge 2025</sub>
</p>
