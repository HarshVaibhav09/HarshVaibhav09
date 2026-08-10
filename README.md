## Hi, I'm Harsh 👋

AI Engineer and backend developer. B.Tech from **NIT Jalandhar (2026)**, based in Bengaluru.

I build LLM systems that answer from real documents — and that know when to stop and hand
off to a human. Making an agent that answers everything is easy; that last part is usually
what separates a demo from something you'd put in front of a paying customer.

💼 **Open to full-time SDE and AI Engineer roles.**

---

## 🚀 Projects

### [OpsPilot](https://github.com/HarshVaibhav09/OpsPilot) · [Live →](https://ops-pilot-phi.vercel.app)
**Document intelligence for logistics ops teams.** Upload rate cards, SOPs, and contracts,
then ask questions instead of digging through PDFs.
`FastAPI` `React` `ChromaDB` `Groq` `Docker`

Hybrid retrieval (dense + BM25, reciprocal rank fusion) hits **0.90 recall@5 vs 0.65
dense-only**, with 0.90 faithfulness on RAGAS. Live at sub-3s p50. Type-aware streaming
ingestion handles 80-page PDFs at constant memory; a heuristic-first classifier resolves
75% of documents with zero LLM calls.

### [MailWarden](https://github.com/HarshVaibhav09/MailWarden)
**A multi-agent system that runs a support inbox end to end.** Built during my work at
ERP BOSS.
`LangGraph` `LangChain` `Groq` `Gemini` `Gmail API` `OAuth 2.0`

An 8-node LangGraph workflow routing threads by intent — **95%+ classification accuracy
across 50+ live threads, 80% less manual handling.** The proofreader is a *separate*
agent, because a model checking its own output approves almost anything. The rewrite loop
is bounded: when the retry budget runs out, a human gets it instead of the fourth-best guess.

### [BookWise](https://github.com/HarshVaibhav09/BookWise) · [Live →](https://university-library-management-syste-nine.vercel.app/)
**University library platform with a real approval workflow.** The less glamorous project,
and the one where I had to think about concurrency.
`Next.js 15` `TypeScript` `Drizzle` `Neon Postgres` `Upstash`

Borrow requests move through admin approval as a genuine state machine, with rate-limited
auth and ID verification — plus the question of what happens when two people request the
last copy at once.

---

## 🛠 Stack

- **AI/LLM** — LangChain · LangGraph · RAG · hybrid retrieval · Pinecone · ChromaDB · RAGAS
- **Backend** — Python · FastAPI · Node.js · Express · OAuth 2.0 · JWT
- **Data** — PostgreSQL · MongoDB · Pandas · NumPy
- **Frontend** — React · Next.js · TypeScript · Tailwind
- **Infra** — Docker · AWS · Git · Vercel

---

## 💼 Experience

- **AI Automation Engineer** · ERP BOSS · *Oct–Dec 2025*
  Built MailWarden (above) — LangGraph orchestration, Gmail API over OAuth 2.0.

- **AI Intern** · Mirai School of Technology · *Jul–Aug 2025*
  n8n automation pipelines, cutting manual operational effort by 80%.

**Also** — Smart India Hackathon 2024 national qualifier · GDSC NIT Jalandhar web team · 350+ LeetCode (1600+)

---

📫 **vaibhavharsh08@gmail.com** · [LinkedIn](https://linkedin.com/in/harsh-vbhv) · [Resume](https://drive.google.com/file/d/11D1M5Vjys6mBk7s1xKDfX1akvWcCRTIm/view?usp=sharing)
