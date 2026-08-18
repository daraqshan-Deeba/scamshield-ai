# 🔄 ScamShield AI Agent Workflow

This document details the multi-agent orchestration, coordination pipeline, and structural schemas used by the **ScamShield AI** investigation system.

---

## ⚡ Investigation Pipeline Sequence

The pipeline operates in three distinct phases: **Parallel Analysis**, **Evidence Fusion**, and **Decision Output**.

```text
       ┌───────────┐
       │   INPUT   │
       └─────┬─────┘
             │
      ┌──────┼──────┐
      ▼      ▼      ▼
    ┌───┐  ┌───┐  ┌───┐
    │Job│  │Rec│  │URL│   [Phase 1: Parallel Investigation]
    └───┬┘  └──┬┘  └──┬┘
        │      │      │
        └──────┼──────┘
               ▼
        ┌─────────────┐
        │  Evidence   │   [Phase 2: Fusion]
        └──────┬──────┘
               ▼
        ┌─────────────┐
        │  Decision   │   [Phase 3: Risk & Rec Engine]
        └─────────────┘
```

---

## 🔎 Agent Descriptions and Schemas

To ensure strict data structures, each agent interacts with the Gemini API using JSON schema constraints (`responseSchema` configurations).

### Phase 1: Parallel Investigation Agents

#### 1. Job Analysis Agent
- **Input:** Job Description (Text) or Screenshot (Image).
- **Goal:** Identify unrealistic job demands, salary inconsistencies, payment requests, and linguistic markers of scams.
- **Output JSON Schema:**
```json
{
  "redFlags": [
    {
      "indicator": "string (e.g. Unrealistic salary)",
      "confidence": "high | medium | low",
      "excerpt": "string (evidence quote from text)"
    }
  ],
  "jobCategory": "string",
  "salaryRealism": "highly_unrealistic | suspicious | normal"
}
```

#### 2. Recruiter Verification Agent
- **Input:** Recruiter name, email, platform (e.g. Telegram, WhatsApp, Email, LinkedIn), and message body.
- **Goal:** Identify channel mismatch (using chat apps instead of corporate tools), email domain spoofing, and high-pressure text patterns.
- **Output JSON Schema:**
```json
{
  "inconsistencies": [
    {
      "type": "string (e.g. Domain mismatch)",
      "details": "string",
      "severity": "high | medium | low"
    }
  ],
  "recruiterIdentityStatus": "verified | unverified | suspicious"
}
```

#### 3. URL Threat Agent
- **Input:** Links/URLs provided in the job post.
- **Goal:** Analyze domain structure, look for squatting (e.g. `google-jobs-career.com`), redirection chains, and potential phishing hooks.
- **Output JSON Schema:**
```json
{
  "suspiciousUrls": [
    {
      "url": "string",
      "category": "domain_squatting | phishing | unknown",
      "riskLevel": "high | medium | low",
      "reason": "string"
    }
  ]
}
```

---

### Phase 2: Evidence Fusion Agent

#### 4. Evidence Agent
- **Input:** Collected outputs from Job, Recruiter, and URL Agents.
- **Goal:** Compile all red flags, remove duplicates, verify logical connections, and categorize findings by severity levels.
- **Output JSON Schema:**
```json
{
  "evidenceFeed": [
    {
      "id": "string (uuid)",
      "severity": "critical | warning | info",
      "title": "string",
      "description": "string",
      "sourceAgent": "job | recruiter | url"
    }
  ]
}
```

---

### Phase 3: Risk & Decision Agent

#### 5. Risk & Decision Agent
- **Input:** Fused evidence feed from the Evidence Agent.
- **Goal:** Compute the overall 0-100 risk score, define the risk band (Low, Medium, High), and generate clear actionable instructions for the candidate.
- **Output JSON Schema:**
```json
{
  "riskScore": "integer (0-100)",
  "riskLevel": "low | medium | high",
  "recommendation": {
    "summary": "string (e.g., Do not proceed with this offer)",
    "steps": ["string (bullet points of action steps)"]
  }
}
```
