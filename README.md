# scamshield-ai
Agentic AI platform that investigates job postings and recruitment opportunities for scam risks.

# 🛡️ ScamShield AI

### The AI Trust Layer for Recruitment

> **Don't just detect a scam. Investigate it.**

ScamShield AI is an **Agentic AI-powered recruitment trust platform** designed to help students, fresh graduates, job seekers, freelancers, and career switchers investigate suspicious job opportunities before sharing sensitive information, clicking unknown application links, or making payments.

---

## 🚨 The Problem

Fake job postings and recruitment scams are becoming increasingly difficult to identify.

Scammers can:

* Create convincing job descriptions
* Impersonate legitimate recruiters
* Use professional-looking communication
* Direct applicants to fraudulent application websites
* Request payments or sensitive information
* Create urgency and pressure victims into acting quickly

A job seeker may therefore see a seemingly legitimate opportunity while missing important warning signs.

The challenge isn't simply:

> **"Is this job fake?"**

The real challenge is:

> **"Can we investigate the opportunity using multiple signals and provide evidence that helps the user make a safer decision?"**

That's the problem **ScamShield AI** is designed to address.

---

## 💡 The Solution

ScamShield AI acts as a **digital trust layer between job seekers and recruitment opportunities**.

Instead of depending on a single AI classification, the platform uses an **agentic investigation workflow**.

### 🔄 Core Concept

```text
┌───────────────┐
│  User Input   │
│               │
│ Job Posting   │
│ Recruiter Msg │
│ Screenshot    │
│ Application   │
│ URL           │
└───────┬───────┘
        │
        ▼
┌───────────────────┐
│  AI Investigation │
│    Orchestrator   │
└─────────┬─────────┘
          │
          ▼
┌─────────────────────────────────┐
│       Specialized Agents        │
│                                 │
│  Job Analysis                   │
│  Recruiter Verification         │
│  URL Threat Analysis            │
└───────────────┬─────────────────┘
                │
                ▼
┌─────────────────────────┐
│    Evidence Collection  │
│       & Fusion          │
└─────────────┬───────────┘
              │
              ▼
┌─────────────────────────┐
│    Risk & Decision      │
│         Agent           │
└─────────────┬───────────┘
              │
              ▼
┌─────────────────────────┐
│      TRUST REPORT       │
│                         │
│  Risk Score             │
│  Evidence               │
│  Recommended Action     │
└─────────────────────────┘
```

### 🎯 Key Output

Every investigation is designed around three things:

| Output                 | Purpose                                  |
| ---------------------- | ---------------------------------------- |
| **Risk Score**         | 0–100 assessment of the opportunity      |
| **Evidence**           | Findings discovered during investigation |
| **Recommended Action** | Guidance based on the investigation      |

---

## 📥 What Can Users Submit?

ScamShield AI is designed to accept multiple forms of recruitment evidence:

* 📄 **Job Posting**
* 💬 **Recruiter Message**
* 🖼️ **Screenshot**
* 🔗 **Application URL**

This allows the system to investigate opportunities across different formats rather than relying only on text from a job description.

---

## 🤖 Agentic AI Architecture

ScamShield uses specialized AI agents, with each agent responsible for a particular investigation task.

```text
                         USER INPUT
                             │
            ┌────────────────┼────────────────┐
            │                │                │
            ▼                ▼                ▼
       Job Posting      Recruiter Msg    URL / Screenshot
            │                │                │
            ▼                ▼                ▼
      ┌──────────┐     ┌──────────────┐   ┌────────────┐
      │   Job    │     │  Recruiter   │   │    URL     │
      │  Agent   │     │ Verification │   │   Threat   │
      │          │     │    Agent     │   │   Agent    │
      └────┬─────┘     └──────┬───────┘   └─────┬──────┘
           │                  │                  │
           └──────────────────┼──────────────────┘
                              ▼
                     ┌─────────────────┐
                     │  Evidence Agent │
                     └────────┬────────┘
                              │
                              ▼
                     ┌─────────────────┐
                     │ Risk & Decision │
                     │      Agent      │
                     └────────┬────────┘
                              │
                              ▼
                     ┌─────────────────┐
                     │   TRUST REPORT  │
                     │                 │
                     │ Risk Score      │
                     │ Evidence        │
                     │ Recommendation  │
                     └─────────────────┘
```

---

## 🧠 Specialized Agents

### 1. 🔍 Job Analysis Agent

Analyzes the job posting for recruitment-related red flags.

It is designed to identify signals such as:

* Suspicious language
* Unrealistic claims
* Unusual recruitment patterns
* Potential payment requests
* Pressure or urgency tactics
* Other recruitment red flags

---

### 2. 👤 Recruiter Verification Agent

Checks the consistency between:

* Recruiter information
* Company information
* Job opportunity
* Recruitment claims

The objective is to identify inconsistencies that may require further verification.

---

### 3. 🔗 URL Threat Agent

Analyzes application links and domain-related risk signals.

The planned architecture supports integration with **URL/domain reputation intelligence** to investigate suspicious application links.

---

### 4. 🧾 Evidence Agent

Collects and organizes findings from the investigation agents.

Instead of presenting an unexplained AI decision, ScamShield aims to connect the final assessment with the evidence discovered during the investigation.

---

### 5. ⚖️ Risk & Decision Agent

Combines the investigation findings and produces the final assessment.

```text
Investigation Findings
         │
         ▼
┌─────────────────────┐
│ Risk & Decision     │
│       Agent         │
└──────────┬──────────┘
           │
           ▼
    ┌──────────────┐
    │ Risk Score   │
    │ Evidence     │
    │ Recommendation│
    └──────────────┘
```

---

# 🏗️ System Architecture

The proposed system consists of several layers:

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
              │                  │
              │ Risk Score       │
              │ Evidence         │
              │ Recommendation   │
              └──────────────────┘
```

---

## ⚙️ Investigation Workflow

The intended MVP workflow is:

```text
User
  │
  ▼
Submit Job / Message / Screenshot / URL
  │
  ▼
AI Orchestrator
  │
  ▼
Specialized Investigation Agents
  │
  ├── Job Analysis
  ├── Recruiter Verification
  └── URL Threat Analysis
  │
  ▼
Evidence Collection
  │
  ▼
Evidence Fusion
  │
  ▼
Risk & Decision
  │
  ▼
Risk Score + Evidence + Recommendation
```

### 🔎 Investigation Philosophy

ScamShield is designed to move from:

```text
Input
  ↓
Investigation
  ↓
Evidence
  ↓
Risk Assessment
  ↓
Explainable Decision
```

rather than simply:

```text
Input
  ↓
"SCAM" / "SAFE"
```

---

# 📊 Risk Assessment

ScamShield is designed to generate a **0–100 Risk Score**.

The assessment is intended to consider multiple signals instead of relying on a single indicator.

```text
Multiple Signals
       │
       ▼
Evidence Collection
       │
       ▼
Evidence Fusion
       │
       ▼
Risk Assessment
       │
       ▼
0 ─────────────────────────── 100
Low Risk                  High Risk
```

> **Note:** The scoring methodology and thresholds will be refined during MVP development and evaluation.

---

# 🛠️ Technology Stack

| Layer                    | Technology                            |
| ------------------------ | ------------------------------------- |
| 🌐 Web Layer             | React / JavaScript                    |
| 🧠 AI Layer              | LLM-based Agent Architecture          |
| 🤖 Agent Architecture    | AI Orchestrator + Specialized Agents  |
| 👁️ Multimodal Analysis  | Screenshot / Visual Evidence Analysis |
| 🔐 Security Intelligence | URL / Domain Reputation APIs          |
| 🗄️ Data Layer           | Supabase / PostgreSQL                 |
| ☁️ Deployment            | Cloud-ready Architecture              |

The technology stack follows the architecture proposed for the project during the idea submission phase.

---

# 📁 Project Structure

```text
scamshield-ai/
│
├── README.md
├── .gitignore
├── LICENSE
│
├── docs/
│   ├── architecture.md
│   ├── agent-workflow.md
│   └── roadmap.md
│
├── frontend/
│   └── README.md
│
├── backend/
│   ├── README.md
│   └── agents/
│       └── README.md
│
├── demo/
│   └── sample-job-post.txt
│
└── screenshots/
    └── architecture.png
```

### 📂 Directory Overview

| Directory / File         | Purpose                                                      |
| ------------------------ | ------------------------------------------------------------ |
| `README.md`              | Project overview, architecture, technology stack and roadmap |
| `docs/`                  | Technical documentation                                      |
| `docs/architecture.md`   | Detailed system architecture                                 |
| `docs/agent-workflow.md` | Agent responsibilities and investigation workflow            |
| `docs/roadmap.md`        | Development and implementation roadmap                       |
| `frontend/`              | Web application layer                                        |
| `backend/`               | Backend and AI investigation layer                           |
| `backend/agents/`        | Specialized AI agent architecture                            |
| `demo/`                  | Example inputs for demonstrating the concept                 |
| `screenshots/`           | Architecture and future product screenshots                  |
| `.gitignore`             | Files excluded from version control                          |
| `LICENSE`                | Project license                                              |

> **Note:** Some components are currently part of the proposed architecture and implementation roadmap. The repository will evolve as the MVP is developed.

---

# 🔐 Reliability & Security

AI-based security systems can produce:

* False positives
* False negatives
* Hallucinated conclusions

ScamShield therefore considers several reliability challenges.

### False Positives

**Mitigation:**

* Multiple signals
* Confidence thresholds
* Evidence aggregation

### AI Hallucination

**Mitigation:**

* Evidence-backed outputs
* Deterministic checks
* Separation between investigation and decision layers

### Changing Scam Patterns

**Mitigation:**

* Updatable detection rules
* Modular agent architecture

### Privacy Risks

**Mitigation:**

* Minimize sensitive data storage
* Avoid unnecessary retention of investigation data

---

# 🎯 Target Audience

ScamShield is initially designed for:

| Audience              | Use Case                               |
| --------------------- | -------------------------------------- |
| 🎓 Students           | Verify opportunities before applying   |
| 👨‍🎓 Fresh Graduates | Investigate unfamiliar recruiters      |
| 💼 Job Seekers        | Assess suspicious job offers           |
| 💻 Freelancers        | Evaluate recruitment opportunities     |
| 🔄 Career Switchers   | Verify unfamiliar companies and offers |

---

# 🌍 Impact & Vision

ScamShield aims to help users identify suspicious recruitment opportunities before they become victims of:

* Recruitment fraud
* Suspicious application links
* Social-engineering tactics
* Financial scams
* Identity and data theft

## 📈 Scalability Vision

```text
Individual User
      │
      ▼
College / University
      │
      ▼
Placement Cell
      │
      ▼
Job Platform
      │
      ▼
Enterprise Recruitment Ecosystem
```

## 🔭 Long-Term Vision

> **Build a digital trust layer between job seekers and recruitment opportunities.**

---

# 🚀 Roadmap

## Phase 1 — Idea Submission

* [x] Problem identification
* [x] Proposed solution
* [x] Agentic AI architecture
* [x] System architecture
* [x] Key features
* [x] Technology stack
* [x] Implementation plan

## Phase 2 — MVP / Prototype

* [ ] Web-based job submission
* [ ] Job Analysis Agent
* [ ] Recruiter Verification Agent
* [ ] URL Threat Agent
* [ ] Evidence Agent
* [ ] Risk & Decision Agent
* [ ] Risk scoring
* [ ] Evidence-backed report
* [ ] Screenshot analysis
* [ ] Database integration

## Phase 3 — Evaluation & Improvement

* [ ] Build evaluation dataset
* [ ] Test legitimate and suspicious opportunities
* [ ] Measure false positives
* [ ] Measure false negatives
* [ ] Calibrate risk thresholds
* [ ] Improve detection rules

## Future Expansion

* [ ] Browser extension
* [ ] Job-platform integration
* [ ] Placement-cell dashboard
* [ ] Continuous threat intelligence
* [ ] Multilingual support
* [ ] Enterprise recruitment integration

---

# 🧪 Evaluation

The system should eventually be evaluated using a mixture of:

```text
Legitimate Job Posts
        +
Suspicious Job Posts
        +
Recruitment Scam Examples
        +
Suspicious Application URLs
        +
Recruiter Impersonation Cases
```

### 📏 Potential Evaluation Metrics

| Metric                 | Purpose                                                   |
| ---------------------- | --------------------------------------------------------- |
| Precision              | Measure correctness of positive detections                |
| Recall                 | Measure how many relevant cases are detected              |
| False Positive Rate    | Measure legitimate opportunities incorrectly flagged      |
| False Negative Rate    | Measure scams that escape detection                       |
| Risk-Score Consistency | Measure consistency of assessments                        |
| Evidence Consistency   | Measure consistency between findings and final assessment |

The objective is **not simply to classify a job as "scam" or "safe."**

The goal is to determine whether ScamShield can provide **useful, explainable evidence** that helps a user make a safer decision.

---

# 📚 Research & References

The project concept is supported by research and public information related to recruitment scams, AI-based fraud detection, and multi-agent AI systems.

### References

1. **FTC — Top Scams of 2024**
   Evidence regarding the scale and financial impact of job and employment scams.

2. **Fraud-BERT — Online Recruitment Fraud Detection**
   Research supporting AI/NLP approaches for detecting recruitment fraud.

3. **LLM-Based Multi-Agent Systems Survey**
   Research supporting multi-agent and specialized-agent architectures.

> Full references are documented in the project's Phase 1 presentation.

---

# 👥 Team

### VictoryStack

**Team Lead:** Daraqshan Deeba

**Project:** ScamShield AI

**Hackathon:** OMNIKON — Cybersecurity, Blockchain & Digital Trust

---

# ⚠️ Disclaimer

ScamShield AI is intended as an **investigative decision-support system**.

It does **not** guarantee that a job opportunity is legitimate or fraudulent.

Users should independently verify employers and recruitment opportunities through trusted official channels before:

* Sharing sensitive information
* Making payments
* Clicking unknown application links
* Proceeding with an application

---

# ⭐ My Mission

> **Recruitment scams exploit trust.**

ScamShield AI aims to make that trust:

**Investigable. Explainable. Evidence-backed.**

```text
Submit
  ↓
Investigate
  ↓
Analyze
  ↓
Assess Risk
  ↓
Explain
```

---

## 🛡️ ScamShield AI

> **Don't just detect a scam. Investigate it.**
