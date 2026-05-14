<div align="center">

# Code Envision Management System

**Enterprise B2B SaaS Platform · React 18 · TypeScript · Vercel**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-code--envision--technologies.vercel.app-black?style=flat-square&logo=vercel)](https://code-envision-technologies.vercel.app)
[![TypeScript](https://img.shields.io/badge/TypeScript-97.8%25-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-18.3-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?style=flat-square&logo=vite&logoColor=white)](https://vite.dev/)
[![Status](https://img.shields.io/badge/Status-Active%20Development-22C55E?style=flat-square)]()
[![Deployed on Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-black?style=flat-square&logo=vercel)](https://vercel.com/)

</div>

---

## Overview

The official website and portfolio platform for **[Code Envision Technologies](https://codeenvisiontechnologies.com)** — a software development company delivering enterprise-grade ERP, CRM, AI/ML, GenAI, Web Applications, and Cloud solutions to clients across 15+ industries globally.

This is a full B2B SaaS marketing and lead generation platform with 18+ pages, 6 detailed service verticals, 4 industry pages, a live case study portfolio, careers portal, and an AI-powered chat assistant — all built with React 18, TypeScript, and Shadcn/ui.

🌐 **Live:** [code-envision-technologies.vercel.app](https://code-envision-technologies.vercel.app)  
🏢 **Company:** [codeenvisiontechnologies.com](https://codeenvisiontechnologies.com)  
📦 **Repo:** [github.com/Hamid-GenAI-Eng/code-envision-management-system](https://github.com/Hamid-GenAI-Eng/code-envision-management-system)

> ⚠️ **Active Development** — Features and pages are continuously being added and improved.

---

## Features

- **18+ Page Application** — Home, Services, Industries, About, Case Studies, Contact, Careers, Insights, Legal
- **6 Service Detail Pages** — ERP, CRM, Web Apps, AI/ML, GenAI & RAG, Cloud & DevOps
- **4 Industry Verticals** — Financial Services, Healthcare, Manufacturing, E-commerce
- **Case Studies Portfolio** — 6 real-world projects with quantified business results
- **Careers Portal** — 6 open roles with full application form and resume upload
- **Contact & Lead Gen** — Budget qualification form with EmailJS integration
- **AI Chatbot Assistant** — Floating widget with quick actions and conversation history
- **Premium Design System** — Cinematic hero, enterprise gradients, motion animations
- **Dark / Light Mode** — Full theme support via Next Themes
- **Fully Responsive** — Mobile-first with Tailwind CSS breakpoints
- **SEO Ready** — Semantic HTML, proper heading hierarchy, Google Site verification

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Language** | TypeScript (97.8%) |
| **UI Library** | React 18.3 |
| **Build Tool** | Vite 5.4 + SWC |
| **Styling** | Tailwind CSS 3.4 |
| **UI Components** | Shadcn/ui · 20+ Radix UI primitives |
| **Router** | React Router DOM 6.30 |
| **Forms** | React Hook Form 7 + Zod 3.25 |
| **Data Fetching** | TanStack React Query v5 |
| **Email** | EmailJS Browser 4.4 |
| **Charts** | Recharts 2.15 |
| **Theming** | Next Themes |
| **Icons** | Lucide React |
| **Notifications** | Sonner |
| **Deployment** | Vercel |

---

## Project Structure 
```
code-envision-management-system/
├── src/
│   ├── pages/
│   │   ├── Index.tsx                  # Home / landing page
│   │   ├── Services.tsx               # Services overview
│   │   ├── Industries.tsx             # Industries overview
│   │   ├── About.tsx                  # Company story & values
│   │   ├── CaseStudies.tsx            # Project portfolio
│   │   ├── Contact.tsx                # Contact form & info
│   │   ├── Careers.tsx                # Job listings & applications
│   │   ├── Insights.tsx               # Blog / knowledge base
│   │   ├── PrivacyPolicy.tsx          # Legal
│   │   ├── TermsOfService.tsx         # Legal
│   │   ├── NotFound.tsx               # 404 page
│   │   ├── services/
│   │   │   ├── ERPService.tsx         # ERP solutions detail
│   │   │   ├── CRMService.tsx         # CRM solutions detail
│   │   │   ├── WebAppsService.tsx     # Web apps detail
│   │   │   ├── AIMLService.tsx        # AI/ML detail
│   │   │   ├── CloudService.tsx       # Cloud & DevOps detail
│   │   │   └── GenAIService.tsx       # Generative AI detail
│   │   └── industries/
│   │       ├── FinancialServices.tsx  # Finance vertical
│   │       ├── Healthcare.tsx         # Healthcare vertical
│   │       ├── Manufacturing.tsx      # Manufacturing vertical
│   │       └── Ecommerce.tsx          # E-commerce vertical
│   ├── components/
│   │   ├── EnterpriseNavigation.tsx   # Responsive header & nav
│   │   ├── Hero.tsx                   # Cinematic hero section
│   │   ├── About.tsx                  # About section
│   │   ├── Services.tsx               # Services showcase
│   │   ├── TechnologyStack.tsx        # Tech stack display
│   │   ├── Projects.tsx               # Featured projects
│   │   ├── Contact.tsx                # Contact form component
│   │   ├── Footer.tsx                 # Footer with links
│   │   ├── ChatBot.tsx                # AI chat assistant widget
│   │   └── ui/                        # Shadcn/ui base components
│   ├── App.tsx                        # Router & provider setup
│   ├── main.tsx                       # React entry point
│   └── index.css                      # Global styles & design tokens
├── public/                            # Static assets
├── vite.config.ts
├── tailwind.config.ts
├── tsconfig.json
├── components.json                    # Shadcn/ui metadata
├── eslint.config.js
├── vercel.json
└── package.json

```

---

## Getting Started

### Prerequisites

- Node.js 18+

### Installation

```bash
git clone https://github.com/Hamid-GenAI-Eng/code-envision-management-system.git
cd code-envision-management-system
npm install
```

### Environment Setup

Create a `.env` file for EmailJS integration:

```env
VITE_EMAILJS_SERVICE_ID=your-service-id
VITE_EMAILJS_TEMPLATE_ID=your-template-id
VITE_EMAILJS_PUBLIC_KEY=your-public-key
```

### Run Locally

```bash
npm run dev
```

Opens at `http://localhost:8080`

---

## Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start development server |
| `npm run build` | Production build |
| `npm run build:dev` | Dev-mode build |
| `npm run preview` | Preview production build locally |
| `npm run lint` | Run ESLint |

---

## Services Covered

| Service | Highlights |
|---|---|
| **ERP Software** | Financial Mgmt · Supply Chain · HR & Payroll |
| **CRM Solutions** | Lead Management · Sales Analytics · Support |
| **Web Applications** | React/Next.js · PWA · Enterprise Portals |
| **AI / ML / CV** | Predictive Analytics · Computer Vision · NLP |
| **GenAI & RAG** | AI Chatbots · Document AI · Custom LLMs |
| **Cloud & DevOps** | AWS/Azure/GCP · CI/CD · Microservices |

---

## Company Stats

| Metric | Value |
|---|---|
| Projects Delivered | 500+ |
| Client Satisfaction | 98% |
| Industries Served | 15+ |
| Enterprise Clients | 50+ |
| System Uptime | 99.9% |
| Support | 24/7 |

---

## Deployment

Deployed on **Vercel** with automatic CI/CD. Every push to `main` triggers a fresh production deployment.

```bash
vercel --prod
```

---

## Built By

**[Code Envision Technologies](https://codeenvisiontechnologies.com)**

Developed by **Hamid Saifullah** — Tech Lead at [Code Envision Technologies](https://codeenvisiontechnologies.com)

[![GitHub](https://img.shields.io/badge/GitHub-Hamid--GenAI--Eng-181717?style=flat-square&logo=github)](https://github.com/Hamid-GenAI-Eng)
[![Portfolio](https://img.shields.io/badge/Portfolio-hamid--saifullah-black?style=flat-square&logo=vercel)](https://hamid-saifullah-portfolio-nexus.vercel.app)
[![Code Envision Technologies](https://img.shields.io/badge/Company-Code%20Envision%20Technologies-0A66C2?style=flat-square)](https://codeenvisiontechnologies.com)
