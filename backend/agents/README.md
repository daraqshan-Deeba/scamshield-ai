# 🤖 ScamShield Specialized AI Agents

This directory holds the implementation for the individual agent files, each structured to handle specific investigation elements using Gemini API structured output formats.

---

## 📂 Agent Files (To Be Implemented)

- **`orchestrator.js`**: Core pipeline router. Receives data from the API endpoint, fires parallel analysis queries to the specialized agents, and pipes results to the evidence and decision agents.
- **`jobAgent.js`**: Analyzes job posting text or screenshot image input for linguistic flags and unrealistic benefits.
- **`recruiterAgent.js`**: Matches recruiters with their claimed companies and platforms. Flags communication via informal chat apps (Telegram, WhatsApp) for professional roles.
- **`urlAgent.js`**: Analyzes linked sites to detect domain spoofing or redirects.
- **`evidenceAgent.js`**: Filters, collates, and compiles observations from all three analysis agents into a single unified JSON feed.
- **`decisionAgent.js`**: Calculates the final 0–100 risk score and compiles recommended action steps based on overall findings.
