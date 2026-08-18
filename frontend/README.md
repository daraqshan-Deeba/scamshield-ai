# 🌐 ScamShield AI Frontend

This folder will house the user interface layer of ScamShield AI, designed to let job seekers submit information and review detailed Trust Reports.

---

## 🛠️ Technology Stack
- **Framework:** React (Vite-based starter)
- **Styling:** Vanilla CSS design tokens (custom variables, HSL colors, dark/light theme options)
- **Libraries:** Charting / UI helper libraries (optional, keeping minimal dependencies for speed)

---

## 📁 Key Components (To Be Implemented)
- `App.jsx`: Main interface wrapper managing current view (Dashboard vs. History) and scan state.
- `components/TrustGauge.jsx`: Circular visual meter depicting computed risk score (0-100) with color dynamics.
- `components/EvidenceFeed.jsx`: Interactive timeline sorting verified positive indicators and warning flags.
- `components/SearchHistory.jsx`: Quick sidebar accessing past investigations.
- `components/InvestigationReport.jsx`: Detail container grouping report summaries and next steps.

---

## 🚀 Running the Frontend (Planned)
Inside the `frontend/` directory, run:
```bash
npm install
npm run dev
```
The application will be accessible at `http://localhost:5173`.
