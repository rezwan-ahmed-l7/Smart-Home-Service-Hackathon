# Smart Home Service Automation

<p align="center">
  <a href="https://www.baust.edu.bd" target="_blank">
    <img src="https://img.shields.io/badge/BAUST , SAIDPUR-059669?style=for-the-badge&logo=google-scholar&logoColor=white" alt="BAUST" />
  </a>
  <img src="https://img.shields.io/badge/HACKATHON-000000?style=for-the-badge&logo=devdotto&logoColor=white" alt="Hackathon" />
  <a href="https://baustcsefest2026.lovable.app/" target="_blank">
    <img src="https://img.shields.io/badge/CSE%20FEST%202026-4285F4?style=for-the-badge&logo=rocket&logoColor=white" alt="CSE Fest" />
  </a>
</p>

<p align="center">
  <strong>GC BAUST CSE Fest 2026 Hackathon</strong> — A premium React platform that matches customers with trusted local providers, schedules jobs, tracks progress live, and handles demo payments + ratings.
</p>

**Live Demo:** [https://smart-home-service-hackathon.onrender.com](https://smart-home-service-hackathon.onrender.com)

---

## Highlights

- **End-to-end service flow** — request → smart match → accept → track → pay → rate
- **Explainable Match Score** with urgency boost and auto-assign best provider
- **Role-based workspaces** for Customer and Provider
- **Demo checkout** (bKash, Nagad, Card, Cash on Service) with invoice
- **Double-booking prevention** on active provider time slots
- **Frosted-glass UI** (custom selects, date picker) — fully client-side, no backend required

---

## About The Project

Arranging home services (AC repair, plumbing, electrical, cleaning, moving, etc.) usually means several manual steps — finding providers, checking availability, comparing options, and following up.

**Smart Home Service** automates that flow end-to-end: customers describe what they need and get ranked provider matches instantly; providers manage incoming jobs through a clean dashboard and update status in real time.

Everything runs in the browser with **LocalStorage** — clone, install, and try it in under a minute.

---

## Live Surfaces

| Surface | URL | Purpose |
| --- | --- | --- |
| Live App | [smart-home-service-hackathon.onrender.com](https://smart-home-service-hackathon.onrender.com) | Full product demo |
| Landing | `/` | Public marketing + Get Started |
| Sign in / Sign up | `/login`, `/signup` | Customer & Provider accounts |
| Customer home | `/` (after login) | Browse services + request form |
| Match results | `/match/:id` | Ranked providers + auto-assign |
| Tracking | `/tracking/:id` | Status, payment, invoice, rating |
| My Requests | `/my-requests` | Customer history |
| Provider Dashboard | `/provider` | Accept jobs + status workflow |

---

## Features

### Customer
- Browse & search service categories
- Guided request form (location, date, time, urgency, problem details, optional photo)
- Smart provider matching with a visible Match Score
- One-click **Auto Assign Best Provider**
- Live status tracking (Requested → Accepted → On the Way → In Progress → Completed)
- Demo payment + digital invoice
- One-time star rating + review
- Request history ("My Requests")

### Provider
- Role-based dashboard
- Incoming job filters (Active / History, Urgency, Sort)
- Accept or reject jobs
- Full status workflow
- Payment status visibility (Paid / Unpaid + amount)
- Customer rating overview
- Double-booking prevention on active time slots

### System
- Urgency-aware matching algorithm
- Frosted-glass UI components (custom date picker, selects)
- LocalStorage persistence for accounts, requests, and bookings

---

## Application Workflow

<table>
<tr>
<td width="45%">

### 1. Sign In / Sign Up

Users choose their role — **Customer** or **Provider** — and sign in with their account details. New users can create an account in seconds.

Features demonstrated:

- Role-based login (Customer / Provider)
- Simple, guided account creation
- Clean, welcoming first impression

</td>
<td width="55%">

<img src="https://github.com/user-attachments/assets/afd9c280-8129-4ea4-9855-7d7f2fc5f4d5" width="100%">

</td>
</tr>

<tr>
<td width="45%">

### 2. Browse & Select a Service

Customers land on a clean service-selection page where they can search or pick from categories like plumbing, electrical, cleaning, and more.

Features demonstrated:

- Live search across services
- Category-based browsing
- Simple, guided entry point into the request flow

</td>
<td width="55%">

<img src="https://github.com/user-attachments/assets/35fbc4f2-993d-4d38-ac99-4560f2284bcf" width="100%">

</td>
</tr>

<tr>
<td width="45%">

### 3. Smart Provider Matching

Once a request is submitted, the app scores every eligible provider using the matching algorithm (expertise, availability, distance, rating, price, urgency) and ranks them.

Features demonstrated:

- Visible Match Score per provider
- Match reasons (why this provider was suggested)
- One-click **Auto Assign Best Provider**

</td>
<td width="55%">

<img src="https://github.com/user-attachments/assets/b75b8d4a-07cc-4b89-af8c-bae782eb5698" width="100%">

</td>
</tr>

<tr>
<td width="45%">

### 4. Provider Dashboard

Providers manage every incoming job from a single workspace — accepting, rejecting, and progressing jobs through the full status workflow.

Features demonstrated:

- Active jobs / completed / rating stats
- Filter by urgency, search, and sort
- Accept, reject, and update job status in real time

</td>
<td width="55%">

<img src="https://github.com/user-attachments/assets/9bb3ed6c-ab35-41e3-9f02-0291a97d785a" width="100%">

</td>
</tr>
</table>

---

## Matching Algorithm

Providers must support the requested service. The score is calculated from:

| Factor | Contribution |
| --- | --- |
| Expertise match | Required (base 30 points) |
| Time availability | Exact slot match = 25 points |
| Distance | Closer = higher (up to 15 points) |
| Provider rating | Up to 15 points |
| Price | Lower base price = higher (up to 10) |
| Urgency bonus | Emergency +5, Urgent +3, Normal +0 |

Providers with an active booking at the same date + time are excluded (double-booking prevention).

---

## Quick Start

**Requirements:** Node.js 18+ and npm.

```bash
git clone https://github.com/rezwan-ahmed-l7/Smart-Home-Service-Hackathon.git
cd Smart-Home-Service-Hackathon

npm install
npm run dev
```

Open the local URL Vite prints (usually `http://localhost:5173`).

**No backend, no seed data** — everything lives in your browser's LocalStorage:

| Role | To get started |
| --- | --- |
| Customer | **Sign Up** → **Customer** → username, 11-digit phone, `@gmail.com` email, password (6+ chars) |
| Provider | **Sign Up** → **Provider** → pick a profile (e.g. Rahim Electronics) → fill the rest |

Use the same details on **Sign In** to log back in later. Provider login must use the **same provider profile** chosen at signup.

---

## Full User Flow

### Customer Path
1. Sign up / sign in as **Customer**
2. Search or select a service
3. Fill location, preferred date & time, urgency, contact details (optional photo)
4. Review ranked matches **or** click **Auto Assign Best Provider**
5. Track the request live; complete demo payment when ready
6. After completion → view invoice + submit rating

### Provider Path
1. Sign up / sign in as **Provider** and choose a profile
2. Open Provider Dashboard
3. Accept or reject incoming jobs
4. Progress status: Accepted → On the Way → In Progress → Completed
5. View payment status and customer ratings on completed jobs

---

## Tech Stack

| Technology | Purpose |
| --- | --- |
| React 19 | UI library |
| Vite | Build tool & dev server |
| React Router | Client-side routing |
| Tailwind CSS | Styling |
| Lucide React | Icons |
| LocalStorage | Client-side persistence |

---

## Project Structure

```text
src/
├── components/   # GlassSelect, GlassDatePicker, PaymentPanel
├── context/      # AppContext (auth, requests, payments, ratings)
├── data/         # Mock services & providers
├── pages/        # Landing, Login, Signup, CustomerHome, MatchResult,
│                 # Tracking, MyRequests, ProviderDashboard
├── utils/        # Matching algorithm
├── App.jsx
└── main.jsx
```

---

## Hackathon Marks Alignment

| Criteria | Implementation |
| --- | --- |
| Functionality Completeness | Full request → match → track → pay → complete → rate flow |
| Code Structure & Readability | Clear folders, modular components, readable utils |
| UI/UX Design | Modern frosted-glass interface, responsive layout |
| Unique Features | Match scoring, urgency boost, auto-assign, invoice, double-booking prevention |

---

## Known Limitations / Roadmap

Built as a hackathon MVP within a tight timeframe — next steps if taken further:

- Replace LocalStorage with a real backend (auth, database, cross-device sync)
- Real payment gateway integration (currently a demo checkout flow)
- Automated tests for matching and booking flow
- Prevent duplicate accounts from claiming the same provider profile

---

## Team Members

| Name | Role / Contribution |
| --- | --- |
| **[Rezwan Ahmed](https://github.com/rezwan-ahmed-l7)** — Team Lead | UI/UX, Core Development, Architecture |
| **[Mahathir Mohammad](https://github.com/mahathirmohammad842-coder)** | UI/UX, Frontend Components |
| **[Mubasser Akhuku](https://github.com/Mubasserakhuku)** | Features, Testing, Documentation |

---

## Author

**Rezwan Ahmed**  
B.Sc. Engg. in CSE Student | Aspiring Software Engineer & Learner

---

## License

> [!NOTE]
> This project was built for the GC BAUST CSE Fest 2026 Hackathon.
