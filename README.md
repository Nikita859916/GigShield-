# 🛡️ GigShield — AI-Powered Parametric Income Protection for India's Gig Economy

> **Guidewire DEVTrails 2026 | Phase 1 Submission**
> Protecting the livelihoods of India's food delivery partners, one week at a time.

---

## 📌 Table of Contents

1. [Problem Statement](#problem-statement)
2. [Our Persona: Food Delivery Partners (Zomato / Swiggy)](#our-persona)
3. [Persona-Based Scenarios & Application Workflow](#persona-scenarios--workflow)
4. [Weekly Premium Model & Parametric Triggers](#weekly-premium-model--parametric-triggers)
5. [Platform Choice: Web vs Mobile](#platform-choice)
6. [AI/ML Integration Plan](#aiml-integration-plan)
7. [Tech Stack & Development Plan](#tech-stack--development-plan)
8. [Constraints & Compliance](#constraints--compliance)

---

## Problem Statement

India's food delivery partners (Zomato, Swiggy) are the heartbeat of the urban food economy — yet they are completely exposed to uncontrollable income shocks. A heavy monsoon, a civic curfew, or a severe AQI spike can wipe out 1–3 days of a worker's weekly earnings with zero recourse.

**GigShield** is a parametric, AI-powered income protection platform built exclusively for food delivery gig workers. When a qualifying disruption is detected, GigShield automatically initiates a claim and processes a payout — no forms, no waiting, no friction.

---

## Our Persona

**Segment: Food Delivery Partners — Zomato & Swiggy (Two-Wheeler Riders)**

### Who They Are

| Attribute | Details |
|-----------|---------|
| **Age Range** | 20–35 years |
| **Primary Earnings** | ₹8,000–₹18,000/month |
| **Work Pattern** | 8–12 hrs/day, 6–7 days/week |
| **Income Cycle** | Weekly platform payouts |
| **Primary Device** | Android smartphone (budget tier) |
| **Location** | Metro cities & Tier-1 cities (Mumbai, Delhi, Bengaluru, Hyderabad, Chennai, Pune) |
| **Key Vulnerability** | 100% outdoor, weather-dependent work on two-wheelers |

### Why This Persona?

Food delivery riders face the **highest exposure** to parametric disruptions because:
- They ride two-wheelers in all weather conditions
- They operate in densely urban areas subject to civic disruptions (curfews, protests, bandhs)
- Heavy rain & floods physically stop delivery operations
- Extreme heat (>42°C) is officially unsafe for outdoor workers
- High pollution (AQI >300) creates dangerous working conditions
- They depend on platform uptime; prolonged app outages eliminate earning opportunities

---

## Persona Scenarios & Workflow

### Scenario 1 — Mumbai Monsoon Flood (Environmental Trigger)

> **Raju**, a Swiggy partner in Kurla, wakes up to IMD flood alerts. Waterlogging makes roads impassable. He loses ₹800–₹1,200 for that day.

**GigShield Flow:**
1. IMD/OpenWeather API detects rainfall > 65mm/hr + flood advisory for Kurla zone
2. GigShield auto-triggers claim for all active policyholders in the affected pin-code cluster
3. Raju receives an in-app notification: *"Disruption detected. Claim auto-filed. Payout in 2 hrs."*
4. ₹600 credited to his UPI/bank account within 2 hours — no action needed from Raju

---

### Scenario 2 — Delhi AQI Emergency (Environmental Trigger)

> **Arjun**, a Zomato partner in Dwarka, is warned by SAFAR that AQI has hit 380 (Severe category). Delhi govt issues advisory suspending outdoor activity.

**GigShield Flow:**
1. SAFAR/CPCB API detects AQI > 300 (Severe) + official government advisory for Delhi NCR
2. Batch payout triggered for all Delhi-registered active policyholders
3. Coverage hours counted from advisory issuance to withdrawal
4. Payout proportional to lost working hours × declared daily earnings

---

### Scenario 3 — Bandh / Civil Curfew (Social Trigger)

> **Priya**, a Swiggy partner in Bengaluru, finds that a city-wide bandh has been called. Both pickup restaurants and drop locations are closed. Delivery platform order volume drops 90%.

**GigShield Flow:**
1. GigShield's social disruption monitor detects: civic authority notification + platform order volume drop > 70% in zone
2. Disruption classified as "Social — Bandh/Curfew"
3. Claim auto-initiated for verified active policyholders in the affected city zone
4. UPI payout sent within the same business day

---

### Scenario 4 — Extreme Heat Advisory (Environmental Trigger)

> **Suresh**, a Zomato partner in Hyderabad, is unable to work during a state government advisory declaring temperatures above 45°C unsafe for outdoor workers.

**GigShield Flow:**
1. IMD Agromet API + State DM office feed detects temp > 43°C + official advisory
2. Affected zone riders with active policies receive automatic payout
3. Coverage window = declared advisory period

---

### Application Workflow (End-to-End)

```
┌─────────────────────────────────────────────────────────────┐
│                    WORKER ONBOARDING                        │
│  Aadhaar + Phone Verification → Platform ID Linking →       │
│  Earnings Declaration → Risk Profile Generated (AI) →       │
│  Weekly Policy Created → UPI Linked for Payouts             │
└───────────────────────┬─────────────────────────────────────┘
                        │
┌───────────────────────▼─────────────────────────────────────┐
│               REAL-TIME DISRUPTION MONITORING               │
│  Weather APIs + AQI APIs + Social Signal APIs →             │
│  Parametric Trigger Evaluation Engine →                     │
│  Zone-Level Alert Classification                            │
└───────────────────────┬─────────────────────────────────────┘
                        │ Trigger Threshold Breached
┌───────────────────────▼─────────────────────────────────────┐
│                 AUTOMATED CLAIM ENGINE                      │
│  Validate Active Policy → Fraud Score Check (AI) →         │
│  Compute Payout Amount → Approve / Flag for Review          │
└───────────────────────┬─────────────────────────────────────┘
                        │
┌───────────────────────▼─────────────────────────────────────┐
│                   INSTANT PAYOUT                            │
│  UPI / Bank Transfer via Razorpay (test mode) →             │
│  Push Notification to Worker → Dashboard Updated            │
└─────────────────────────────────────────────────────────────┘
```

---

## Weekly Premium Model & Parametric Triggers

### Weekly Premium Model

GigShield operates on a **pay-as-you-work week** model aligned with how gig platforms pay their partners.

| Coverage Tier | Weekly Premium | Max Weekly Payout | Best For |
|---------------|---------------|------------------|----------|
| **Basic Shield** | ₹25/week | ₹500/week | New or part-time riders |
| **Standard Shield** | ₹49/week | ₹1,200/week | Full-time riders (avg income) |
| **Pro Shield** | ₹79/week | ₹2,000/week | High-earning experienced riders |

**Premium Calculation Formula (AI-Adjusted):**

```
Weekly Premium = Base Rate
              × Zone Risk Multiplier (0.8–1.4)
              × Seasonal Risk Factor (0.9–1.3)
              × Rider Tenure Discount (max −15%)
              × Claim History Adjustment (+/−10%)
```

- **Zone Risk Multiplier:** Higher for flood-prone/pollution-heavy zones (e.g., Mumbai coastal = 1.4, Pune hills = 0.9)
- **Seasonal Risk Factor:** Higher during monsoon months (Jun–Sep), winter pollution months (Oct–Feb for Delhi)
- **Rider Tenure Discount:** Riders active for 6+ months with no fraudulent claims get a discount
- **Premium is auto-debited weekly** from the rider's platform earnings (with consent), ensuring zero missed premiums

### Parametric Triggers (5 Defined Triggers)

| # | Trigger Name | Data Source | Threshold | Payout Type |
|---|-------------|-------------|-----------|------------|
| 1 | **Heavy Rain / Flood** | IMD, OpenWeatherMap, NDMA alerts | Rainfall > 64.5mm in 24hrs OR official flood advisory for zone | Proportional to disruption hours |
| 2 | **Severe Pollution (AQI)** | SAFAR, CPCB API | AQI > 300 (Severe category) + govt advisory | Fixed daily rate × affected hours |
| 3 | **Extreme Heat** | IMD Agromet, State DM feeds | Temperature > 43°C + official advisory | Fixed daily rate × advisory duration |
| 4 | **Civil Disruption (Bandh/Curfew)** | Civic authority feeds + platform order volume drop | Order volume drop > 70% in zone + verified civil notification | Fixed half-day / full-day payout |
| 5 | **Cyclone / Severe Storm** | IMD cyclone tracker, NDMA | Cyclone warning (Cat 1+) within 100km of worker's registered zone | Full daily payout per declared day |

**All triggers are purely parametric** — no manual claim submission required from the worker. The platform verifies external data sources and initiates the claim automatically.

---

## Platform Choice

**We are building a Progressive Web App (PWA) with a Mobile-First design.**

### Rationale

| Factor | Our Decision | Reason |
|--------|-------------|--------|
| **Primary device** | Android smartphone | Budget Android (4G) is the universal device for delivery riders |
| **App install friction** | PWA (no app store needed) | Workers are reluctant to install new apps; PWA works from a browser link |
| **Offline capability** | Service Worker caching | Riders often operate in low-connectivity zones |
| **Admin dashboard** | Full web app | Insurer/admin dashboards require larger screens for analytics |
| **Push notifications** | PWA Web Push | Critical for instant claim alerts without a native app |
| **Language support** | Hindi + English UI | Workers prefer vernacular; reduces onboarding drop-off |

A native app (Phase 3 stretch goal) may be explored for deeper platform integration (Zomato/Swiggy APIs), but the core MVP is PWA.

---

## AI/ML Integration Plan

### 1. Dynamic Premium Calculation (Risk Scoring Engine)

**Model:** Gradient Boosted Trees (XGBoost / LightGBM)

**Input Features:**
- Worker's registered delivery zone (pin-code cluster)
- Historical weather disruption frequency for that zone (last 3 years)
- Historical AQI data for the zone
- Historical bandh/civil disruption records for the city
- Rider's platform tenure, average weekly earnings, delivery history length
- Seasonal indicators (month, monsoon flag, winter pollution flag)

**Output:** Risk score per zone per week → translated to zone risk multiplier for premium calculation

**Training Data Sources:**
- IMD historical rainfall data (open)
- CPCB historical AQI data (open)
- NDMA historical disaster records (open)
- Mock synthetic rider profiles for initial training

---

### 2. Fraud Detection Engine

**Model:** Isolation Forest + Rule-Based Anomaly Flags (hybrid)

**Fraud Vectors We Address:**

| Fraud Type | Detection Method |
|-----------|-----------------|
| **GPS Spoofing** | Verify last GPS coordinates vs disruption zone boundary; flag if worker claims disruption but GPS shows them in a unaffected zone |
| **Fake Disruption Claims** | Cross-validate against ≥2 independent APIs (e.g., both IMD + NDMA must confirm); single-source not accepted |
| **Duplicate Claims** | Unique policy ID + event ID deduplication; one payout per disruption event per policy |
| **Policy Stacking** | Device fingerprint + Aadhaar match prevents multiple policies for same worker |
| **Claim Timing Anomaly** | Flag if claim filed significantly outside the disruption window |

**Fraud Score:** 0–100; auto-approve <30, manual review 30–70, auto-reject >70

---

### 3. Predictive Risk Modelling (Insurer Dashboard)

**Model:** Time-series forecasting (Prophet / LSTM) for weekly disruption probability per zone

**Use Case:** Insurer can see "Next week: 67% probability of AQI disruption event in Delhi NCR zone" → allows reserve provisioning and reinsurance triggers

---

### 4. Claim Payout Calculation (NLP for Advisory Parsing)

A lightweight NLP classifier will parse government advisories from NDMA/IMD RSS feeds to extract: disruption type, affected zones, start/end time, severity level — enabling fully automated claim window determination.

---

## Tech Stack & Development Plan

### Tech Stack

| Layer | Technology | Rationale |
|-------|-----------|-----------|
| **Frontend** | React (PWA) + Tailwind CSS | Mobile-first, fast, offline-capable |
| **Backend** | Node.js (Express) | Lightweight, fast for API-heavy workload |
| **Database** | PostgreSQL (primary) + Redis (cache) | Reliable relational store + fast session/trigger cache |
| **ML / AI** | Python (FastAPI microservice) + scikit-learn, XGBoost | Separate ML inference service for clean architecture |
| **External APIs** | OpenWeatherMap (free tier), CPCB AQI API, NDMA RSS, mock civic feeds | All free-tier or mock during hackathon |
| **Payments (Mock)** | Razorpay Test Mode / UPI Simulator | Demonstrates payout flow without real transactions |
| **Notifications** | Firebase Cloud Messaging (FCM) | Push notifications via PWA |
| **Hosting** | Vercel (frontend) + Render / Railway (backend) | Free tier, fast deployment |
| **Auth** | OTP via SMS (Twilio trial) + JWT | Simple, frictionless for workers |

### 6-Week Development Plan

```
PHASE 1 (Weeks 1–2): Ideation & Foundation  [Mar 4–20]
  ✅ Problem research & persona finalization
  ✅ System architecture design
  ✅ README documentation (this document)
  ✅ Repository setup
  ✅ UI wireframes (Figma)
  ✅ API integrations scoped & mocked
  ✅ 2-minute strategy video

PHASE 2 (Weeks 3–4): Automation & Protection  [Mar 21–Apr 4]
  → Worker registration & onboarding flow (PWA)
  → Insurance policy creation with weekly pricing UI
  → Dynamic premium calculation (ML model v1)
  → Parametric trigger engine (3–5 triggers with mock APIs)
  → Automated claim initiation logic
  → Claims management dashboard (worker view)
  → 2-minute demo video

PHASE 3 (Weeks 5–6): Scale & Optimise  [Apr 5–17]
  → Advanced fraud detection (GPS validation, anomaly detection)
  → Instant payout simulation (Razorpay test mode)
  → Intelligent dual dashboard (Worker + Insurer/Admin)
  → Predictive analytics for insurers (weekly disruption forecast)
  → Performance optimization & UX polish
  → Final pitch deck (PDF)
  → 5-minute final demo video
```

### Repository Structure

```
gigshield/
├── frontend/           # React PWA
│   ├── src/
│   │   ├── pages/      # Onboarding, Dashboard, Policy, Claims
│   │   ├── components/ # Reusable UI components
│   │   └── services/   # API calls
├── backend/            # Node.js/Express API
│   ├── routes/         # Auth, Policy, Claims, Triggers
│   ├── models/         # DB models
│   └── services/       # Trigger engine, Payout service
├── ml-service/         # Python FastAPI
│   ├── risk_model/     # Premium calculation ML
│   ├── fraud_model/    # Anomaly detection
│   └── data/           # Training data (mock/open)
├── docs/               # Architecture diagrams, wireframes
└── README.md
```

---

## Constraints & Compliance

| Constraint | GigShield Compliance |
|-----------|---------------------|
| **No health/life/accident/vehicle repair coverage** | ✅ GigShield covers ONLY loss of income during external disruptions. No medical, accident, or vehicle-related payouts exist anywhere in the platform. |
| **Weekly pricing model** | ✅ All premiums, coverage tiers, and payout windows are structured on a 7-day (weekly) basis aligned with platform payout cycles. |
| **Persona-specific focus** | ✅ Built exclusively for food delivery partners (Zomato/Swiggy two-wheeler riders). |
| **Parametric triggers only** | ✅ All claims are triggered by verifiable external data (weather APIs, AQI feeds, civic alerts) — not by self-reported incidents. |

---

## Unique Value Propositions

1. **Zero-touch claims** — Workers never need to file a claim. Disruption detected = payout initiated automatically.
2. **Hyper-local risk pricing** — Premiums vary by pin-code cluster, not just city, making pricing fair and accurate.
3. **₹25/week entry point** — Designed to be affordable for the lowest-earning riders.
4. **Vernacular-first UI** — Hindi + English to reduce friction and improve trust.
5. **Transparent trigger dashboard** — Workers can see exactly which conditions trigger a payout, building trust in the product.

---

*GigShield — Because every delivery partner deserves a safety net as reliable as their work ethic.*

> **Team:** [Team Name]
> **Hackathon:** Guidewire DEVTrails 2026
> **Phase 1 Submission Deadline:** March 20, 2026
