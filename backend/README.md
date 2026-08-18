# 🧠 ScamShield AI Backend

This folder contains the server-side logic, API endpoints, database access layers, and the multi-agent investigation system.

---

## 🛠️ Technology Stack
- **Environment:** Node.js
- **Framework:** Express.js
- **AI Integration:** Google Gen AI SDK (`@google/genai`)
- **Storage:** Local JSON Store (`scans_db.json`) for local runs, convertible to Supabase Client for production.
- **File Upload:** Multer (for managing screenshot image buffers)

---

## 🚦 API Endpoints (To Be Implemented)
- `POST /api/investigate`: Orchestrates investigation by parsing job texts, images, recruiter details, and URLs.
- `GET /api/scans`: Fetches history of previous scans.
- `GET /api/scans/:id`: Fetches a single Trust Report.

---

## 🚀 Running the Backend (Planned)
Inside the `backend/` directory, set up your API key:
1. Create a `.env` file from `.env.example`:
   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   PORT=5000
   ```
2. Run development commands:
   ```bash
   npm install
   npm run dev
   ```
Server will boot on `http://localhost:5000`.
