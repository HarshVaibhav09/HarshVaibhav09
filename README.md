## Hi, I'm Harsh 👋

AI Engineer and backend developer. B.Tech from **NIT Jalandhar (2026)**, based in Bengaluru.

Most of what I build lands in the same territory: an LLM that has to answer from real
documents, a backend that has to stay up while it does, and a decision about what
happens when the model isn't sure.

That last part is the one I keep coming back to. Making an agent that answers everything
is easy. Making one that knows when to stop and hand off to a human is harder — and it's
usually what separates a demo from something you'd put in front of a paying customer.
Every system below has an explicit answer to *"what happens when this is wrong."*

💼 **Open to full-time SDE and AI Engineer roles.**

---

## 🚀 Projects

### [OpsPilot](https://github.com/HarshVaibhav09/OpsPilot) · [Live demo →](https://ops-pilot-phi.vercel.app)
**Document intelligence for logistics ops teams.** Upload rate cards, SOPs, vendor
contracts, incident logs — then ask questions instead of digging through PDFs by hand.

`FastAPI` `React` `ChromaDB` `Groq` `Docker`

- **Hybrid retrieval** — dense embeddings + BM25, fused with reciprocal rank fusion.
  **0.90 recall@5 and 0.80 MRR**, against 0.65 for dense-only on my gold query set.
- **Evaluated, not eyeballed** — 0.90 faithfulness, 0.95 answer relevancy on RAGAS.
- **Live at sub-3s p50, sub-6s p95** query latency.
- **Type-aware streaming ingestion** — 80-page PDFs process at constant memory, and a
  heuristic-first classifier resolves 75% of documents with zero LLM calls.
- Every answer cites its source file, page, and section. Follow-up questions resolve
  against prior context.

*The part I'd talk about in an interview:* there's a dev-mode toggle that exposes
similarity scores, the rewritten query, and chunk-level retrieval detail. I built it to
debug my own retrieval quality and kept it, because "the model gave a bad answer" and
"the retriever handed it the wrong chunks" are completely different bugs and you can't
tell them apart without looking.

---

### [MailWarden](https://github.com/HarshVaibhav09/MailWarden)
**A multi-agent system that runs a customer support inbox end to end.** Built during my
work at ERP BOSS. It reads unread threads, works out what each one is, drafts a grounded
reply, and sends it — or flags it for a human when it shouldn't.

`LangGraph` `LangChain` `Groq` `Gemini` `Gmail API` `FastAPI` `OAuth 2.0`

- **8-node LangGraph workflow** routing by intent — complaints go straight to drafting,
  product questions run through query synthesis and retrieval first, spam exits the graph
  before it costs an LLM call.
- **95%+ classification accuracy across 50+ live threads.**
- **Cut end-to-end email handling workload by 80%** with no manual intervention.
- **Deliberate model selection** — Groq for low-latency classification, Gemini for
  reasoning-heavy drafts. Different jobs sit on different latency-vs-cost curves.

*The part I'd defend hardest:* the proofreader is a **separate agent**, with its own
prompt and its own view of the retrieved context. A model checking its own output
approves almost anything — splitting it makes the check adversarial instead of
self-congratulatory. And the rewrite loop is bounded: when the retry budget runs out,
the thread goes to a human rather than sending the fourth-best guess.

---

### [BookWise](https://github.com/HarshVaibhav09/BookWise) · [Live demo →](https://university-library-management-syste-nine.vercel.app/)
**University library platform with a real approval workflow.** The less glamorous
project, and the one where I actually had to think about concurrency.

`Next.js 15` `TypeScript` `Drizzle` `Neon Postgres` `Upstash`

- Borrow requests route through admin approval — a genuine state machine, not a boolean.
- Rate-limited auth, and ID-card verification before an account can borrow anything.
- Forced me to reason about race conditions: what happens when two people request the
  last copy at the same moment.

---

## 💼 Experience

**AI Automation Engineer** — ERP BOSS · *Oct – Dec 2025 · Remote*
Built the multi-agent email triage system above ([MailWarden](https://github.com/HarshVaibhav09/MailWarden))
— LangGraph orchestration, Gmail API integration over OAuth 2.0, and the production
model-selection call between Groq and Gemini.

**AI Intern** — Mirai School of Technology · *Jul – Aug 2025 · Remote*
Shipped n8n-orchestrated automation pipelines including an AI travel planner and a cafe
feedback system, cutting manual operational effort by 80%. Integrated LLM-assisted dev
tooling into team workflows.

---

## 🛠 What I work with

| | |
|---|---|
| **AI / LLM** | LangChain, LangGraph, multi-agent orchestration, RAG pipelines, hybrid retrieval (dense + BM25), Pinecone, ChromaDB, Sentence Transformers, chunking & embedding strategy, RAGAS evaluation |
| **Backend** | Python, FastAPI, Pydantic, Node.js, Express, REST APIs, OAuth 2.0, JWT |
| **Data** | PostgreSQL, MongoDB, SQLite, Pandas, NumPy |
| **Frontend** | React, Next.js, TypeScript, Tailwind |
| **Infra** | Docker, AWS, Git, Vercel, Railway |
| **Also** | C++, DSA — 350+ LeetCode problems, 1600+ rating |

---

## 🏆 Beyond the code

**Smart India Hackathon 2024** — national-level qualifier, representing NIT Jalandhar
among 100,000+ participants.
**GDSC NIT Jalandhar** — Web Development technical team, 2023–2025.

---

## 📖 On how I document things

Every repo here has an architecture diagram and a **Known Limitations** section that
names what's broken, unhandled, or deliberately deferred — unbounded categorization
confidence, silent retrieval failures, ungraceful rate-limit handling. It's all written
down.

I'd rather you hear the rough edges from me than find them in the code. If you're
evaluating me, start there. It'll tell you more than any feature list.

---

## 📫 Reach me

**vaibhavharsh08@gmail.com** · [LinkedIn](https://linkedin.com/in/harsh-vbhv) · [Resume](LINK)

Happy to talk about agent architectures, retrieval that doesn't hallucinate, or why your
RAG pipeline keeps returning the wrong chunks.
