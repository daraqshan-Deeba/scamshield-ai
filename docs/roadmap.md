# 🚀 ScamShield AI Project Roadmap

This document outlines the milestones and releases planned for the **ScamShield AI** platform, from prototype to scale.

---

## 📍 Phase 1: Planning and Architecture (Current)
* [x] **Define Problem & Scope:** Map user needs, target demographics (students, job seekers), and common scam patterns.
* [x] **Design Agent Architecture:** Detail specialized agent roles (Job, Recruiter, URL, Evidence, Decision).
* [x] **Determine Technology Stack:** React for frontend, Express.js for backend orchestration, Gemini 2.5 Flash for agent reasoning, local/Supabase for storage.
* [x] **Map Out Repository:** Establish base directory structure and write core documentation.

---

## 📍 Phase 2: MVP Development & Prototyping
* [ ] **Backend Setup:**
  - Initialize Node/Express application.
  - Setup basic JSON database storage API (`database.js`).
  - Integrate `@google/genai` client.
* [ ] **Specialized Agent Implementation:**
  - Build Job Analysis Agent with structured JSON output prompts.
  - Build Recruiter Verification Agent matching message metadata.
  - Build URL Agent identifying domain squatting.
* [ ] **Orchestrator Setup:**
  - Develop sequential/parallel runner logic that passes data step-by-step to the Evidence and Decision agents.
* [ ] **Frontend Application:**
  - Create Vite-React application.
  - Write Vanilla CSS design tokens and core layouts.
  - Build submission tabs (Text, URL, screenshot file uploads).
  - Implement Trust Gauge, Evidence Feed, and Scan History components.
* [ ] **Multimodal Screenshot Support:**
  - Connect Multer screenshot handler to Gemini multimodal image input pipelines.

---

## 📍 Phase 3: Evaluation, Test, & Refinement
* [ ] **Curate Datasets:** Establish a set of 50 mock recruitment communications (25 legitimate, 25 scam variants) to evaluate accuracy.
* [ ] **Risk Score Calibration:** Fine-tune decision agent math to ensure proper low/medium/high classification boundaries.
* [ ] **User Feedback Cycle:** Beta test the UI with student focus groups. Fix navigation flow shifts and responsiveness.

---

## 📍 Phase 4: Production Integration & Scaling
* [ ] **Database Migration:** Swap local JSON storage with production Supabase PostgreSQL schemas.
* [ ] **Browser Extension:** Develop a lightweight extension to scan active webpage job descriptions on LinkedIn, Indeed, and Upwork directly.
* [ ] **API Security:** Add rate-limiting, user authentication, and data retention opt-outs to prioritize applicant privacy.
