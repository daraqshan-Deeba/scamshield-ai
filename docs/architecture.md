# 🏗️ ScamShield AI System Architecture

This document describes the technical architecture, component breakdown, and system integrations of **ScamShield AI**.

---

## 🗺️ System Architecture Overview

ScamShield AI is designed as a **multi-agent investigation platform** that sits between a job seeker and potential recruitment opportunities. The system comprises three main layers:

1. **Web UI Layer (Frontend):** React web interface where users submit data and view trust reports.
2. **AI Orchestration & Agent Layer (Backend):** Coordinating hub that routes submissions to specialized LLM-based agents.
3. **Data Layer:** Local file-based system (MVP) or Supabase (production) to store scan history, logs, and reputation lists.

```text
┌──────────────────────────────────────┐
│              WEB LAYER               │
│          React / JavaScript          │
└──────────────────────┬───────────────┘
                       │
                       ▼
┌──────────────────────────────────────┐
│          AI ORCHESTRATOR             │
│       Agent Routing & Coordination   │
└──────────────────────┬───────────────┘
                       │
              ┌────────┼────────┐
              ▼        ▼        ▼
           ┌─────┐ ┌────────┐ ┌─────┐
           │ JOB │ │RECRUITER│ │ URL │
           │AGENT│ │  AGENT  │ │AGENT│
           └──┬──┘ └────┬────┘ └──┬──┘
              │         │         │
              └─────────┼─────────┘
                        ▼
              ┌──────────────────┐
              │  EVIDENCE AGENT  │
              │ Evidence Fusion  │
              └────────┬─────────┘
                        │
                        ▼
              ┌──────────────────┐
              │ RISK & DECISION  │
              │      AGENT       │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │   TRUST REPORT   │
              └──────────────────┘
```

---

## 🧩 Core Components

### 1. Web Layer (Frontend)
- **Framework:** React.js powered by Vite.
- **Styling:** Vanilla CSS design tokens (custom typography, responsive grid, HSL-based dark theme, interactive animations).
- **Core Views:**
  - **Submit Dashboard:** Interactive forms with multiple input types (text, screenshot, link).
  - **Trust Report Viewer:** High-fidelity dashboard visualizing risk level, warning indicators, and reasoning.
  - **Scan History:** Quick sidebar navigation for reviewing past results.

### 2. Backend Orchestrator & API
- **Framework:** Express.js running on Node.js.
- **Role:** Handles API routing, runs file upload preprocessing (Multer), orchestrates agents using standard Javascript promises, and saves logs.
- **End-points:**
  - `POST /api/investigate`: Multi-agent pipeline entry point.
  - `GET /api/scans`: Retreive list of historical scans.
  - `GET /api/scans/:id`: Fetch specific scan by ID.

### 3. Specialized AI Agents
The system orchestrates five specialized agents utilizing the Google Gemini API (`gemini-2.5-flash`):

- **Job Analysis Agent:** Reviews the job description for linguistic tricks, salary anomalies, payment requests, or task demands.
- **Recruiter Agent:** Investigates sender credentials, domain alignment (e.g., checking if the email sender is using a public domain like `@gmail.com` to hire for a Fortune 500 company), and communication style.
- **URL Threat Agent:** Checks links for domain squatting, redirects, and potential phishing.
- **Evidence Agent:** Acts as the data synthesizer, fusing duplicate claims, verifying facts, and creating a unified severity-sorted feed.
- **Risk & Decision Agent:** Performs the final evaluation, weighting different types of evidence, computing the overall 0-100 score, and generating a clear action plan.

---

## 💾 Data Flow & Storage

1. **Request Reception:** User posts data to the Express server.
2. **Pre-processing:** Screenshots are prepared as image buffer inputs for multimodal Gemini API ingestion.
3. **Concurrent Execution:** Job, Recruiter, and URL agents execute concurrently.
4. **Sequential Synthesis:** Findings are passed to the Evidence Agent, then to the Decision Agent.
5. **Storage:** The final report is saved to `scans_db.json` (local JSON store) or written to a PostgreSQL database via Supabase client helper.
6. **Response:** Front-end renders the saved JSON response.
