# From Solutions Engineer to Forward Deployed Engineer
### A 26-week roadmap (assumes ~10–15 hrs/week)

**Starting point:** Solid HTML/CSS/JS/React fundamentals, comfortable with git, can hit external APIs from the front end, basic Python exposure from university.

**Gap to close:** Backend/API development, databases/SQL, cloud & deployment, LLM/agent integration, systems design, and DS&A interview fluency.

**Timeline variants:** 5–8 hrs/week → stretch to ~9–12 months. 25+ hrs/week → compress to ~12–14 weeks.

**How to maintain this file:** check off tasks as you go (GitHub renders `- [ ]` as clickable checkboxes and commits the change automatically). At the end of each week, check off what's done and commit with a message like `Week 3 complete`. If you're consistently missing an "on track if" checkpoint, slow down rather than skip ahead; if consistently finishing early, pull next week forward.

---

## Overview

| Phase | Weeks | Focus |
|---|---|---|
| 1 | 1–4 | CS50P (Python) + intro DS&A |
| 2 | 5–10 | Backend engineering, SQL, databases |
| 3 | 11–14 | Docker, cloud, CI/CD |
| 4 | 15–18 | LLM / agent integration |
| 5 | 19–22 | Systems design + interview prep |
| 6 | 23–26 | Capstone project + job search |

**Progress:** `0 / 26 weeks complete` ← update this line manually as you go, it's an easy way to see momentum at a glance.

---

## Phase 1: CS50P + DS&A Foundations (Weeks 1–4)

Harvard's CS50P (free at cs50.harvard.edu/python — sign up, then use the cs50.dev cloud codespace). Organized as 10 lecture+problem-set pairs (0–9) plus a final project. Each pset auto-grades via `check50`.

### Week 1 — CS50P Weeks 0–2: Functions/Variables, Conditionals, Loops
- [x] Sign up at cs50.harvard.edu/python, set up cs50.dev codespace, run `update50`
- [x] Lecture 0 (Functions, Variables)
- [x] Problem Set 0 — Indoor Voice, Playback Speed, Making Faces, Einstein, Tip Calculator
- [x] Lecture 1 (Conditionals)
- [x] Problem Set 1
- [ ] Lecture 2 (Loops)
- [ ] Problem Set 2

**Time split:** ~2–2.5 hrs for lecture 0 + pset 0 (light, mostly setup), ~3–4 hrs each for psets 1 and 2. Total ~10–12 hrs.
**On track if:** all three psets pass `check50`, and you can explain — without looking anything up — what a function signature is, what makes an expression "truthy," and how a `while` loop differs from a `for` loop.

### Week 2 — CS50P Weeks 3–5: Exceptions, Libraries, Unit Tests
- [ ] Lecture 3 (Exceptions)
- [ ] Problem Set 3
- [ ] Lecture 4 (Libraries — pip, third-party packages)
- [ ] Problem Set 4
- [ ] Lecture 5 (Unit Tests — intro to pytest)
- [ ] Problem Set 5

**Time split:** ~10–12 hrs total.
**On track if:** you can write a `try/except` block from memory, install and import a pip package without googling syntax, and write a pytest test function with at least two assertions.

### Week 3 — CS50P Weeks 6–8: File I/O, Regular Expressions, OOP
- [ ] Lecture 6 (File I/O)
- [ ] Problem Set 6
- [ ] Lecture 7 (Regular Expressions)
- [ ] Problem Set 7
- [ ] Lecture 8 (Object-Oriented Programming)
- [ ] Problem Set 8

**Time split:** ~12–14 hrs — the OOP pset is the meatiest one so far, don't rush it.
**On track if:** you can read/write a CSV without reference, write a regex that validates an email format, and define a class with `__init__` and at least one method, and can explain what `self` is doing.

### Week 4 — CS50P Week 9 + light final project + DS&A intro
- [ ] Lecture 9 (Et Cetera — f-strings, type hints, list comprehensions, walrus operator)
- [ ] Problem Set 9
- [ ] CS50P final project — **cap it at 3–5 hrs**, a small CLI tool solving a real annoyance you have. Don't over-invest; Phase 2 produces stronger portfolio work.
- [ ] Watch a short Big-O primer (NeetCode's own ~20 min YouTube video is enough)
- [ ] NeetCode — Arrays & Hashing category, at least 6 of 9: Two Sum, Valid Anagram, Contains Duplicate, Group Anagrams, Top K Frequent Elements, Product of Array Except Self, Valid Sudoku, Encode and Decode Strings, Longest Consecutive Sequence

**On track if:** all 10 CS50P psets complete, and you can solve Two Sum and Valid Anagram from scratch, no notes, in under 15 minutes combined.

---

## Phase 2: Backend & Databases (Weeks 5–10)

### Week 5 — SQL fundamentals
- [ ] SQLBolt (~18 lessons) start to finish
- [ ] Install Postgres locally, or use a free hosted instance (Neon or Supabase)
- [ ] Get a GUI client (DBeaver or TablePlus)
- [ ] Load a sample dataset (Postgres's own "pagila" DVD-rental sample DB works well)
- [ ] Write 10 original queries against the sample DB (not copied from tutorial)

**On track if:** you can write a 3-table JOIN with a WHERE and GROUP BY from scratch, no lookup.

### Week 6 — SQL intermediate + query practice
- [ ] Mode Analytics SQL tutorial, intermediate section
- [ ] Read about what an index is and why full table scans are slow (30–45 min, conceptual only)
- [ ] Answer 5 "business questions" against your dataset requiring joins + aggregation + subqueries

**On track if:** given a new, unfamiliar schema, you can write a correct multi-table query within about 10 minutes.

### Week 7 — REST APIs with FastAPI
- [ ] FastAPI tutorial: First Steps → Path Parameters → Query Parameters → Request Body → Query/Path validations → Body – Multiple Parameters
- [ ] Build a "tasks" CRUD API (in-memory storage): GET /tasks, GET /tasks/{id}, POST /tasks, PUT /tasks/{id}, DELETE /tasks/{id}
- [ ] Manually test all 5 endpoints via the auto-generated Swagger UI at `/docs`

**On track if:** all 5 endpoints work locally, and you can explain what a Pydantic model is doing for you.

### Week 8 — Database-backed API
- [ ] FastAPI docs: "SQL (Relational) Databases" section
- [ ] SQLAlchemy quickstart
- [ ] FastAPI docs: "Security" section (read for concept, OAuth2/JWT)
- [ ] Rewrite tasks API to persist via SQLAlchemy models to Postgres
- [ ] Add a simple API-key header check as first-pass auth

**On track if:** you can restart your API server and your tasks still exist, and you can explain authentication vs. authorization out loud.

### Week 9 — Testing + polish
- [ ] FastAPI docs: "Testing" section (TestClient)
- [ ] Write tests covering all 5 endpoints — at least one happy-path and one failure-path each
- [ ] Write a real README: setup, how to run, how to test

**On track if:** `pytest` runs fully green with at least 10 test cases, and someone unfamiliar with the project could get it running using only your README.

### Week 10 — Server-side third-party API integration
- [ ] Rebuild the old Weather App's API logic as a backend service (not client-side)
- [ ] Add basic response caching (in-memory dict + timestamp check is enough)
- [ ] Handle failure cases: API down, rate-limited, malformed response

**On track if:** you can explain specifically why calling a third-party API directly from the browser is often the wrong architecture.

---

## Phase 3: Docker, Cloud & CI/CD (Weeks 11–14)

### Week 11 — Docker
- [ ] Docker's official "Get Started" tutorial
- [ ] Write a Dockerfile for the FastAPI app
- [ ] Write a docker-compose.yml wiring API + Postgres together

**On track if:** `docker-compose up` from a clean clone brings up the whole Phase 2 project with zero manual setup steps.

### Week 12 — Cloud fundamentals (AWS free tier)
- [ ] Launch a t2.micro/t3.micro EC2 instance on the AWS Free Tier
- [ ] Configure a security group (open the port your API needs)
- [ ] SSH in, install Docker
- [ ] Manually deploy the dockerized app

**Fallback:** if IAM/security-group setup becomes a multi-day blocker, deploy via Render or Railway this week to keep momentum, then circle back to AWS once something is live.
**On track if:** your API is reachable from a public IP/URL, not just localhost.

### Week 13 — CI/CD
- [ ] Write a GitHub Actions workflow that runs on every push: install deps, run pytest
- [ ] Add a deploy step (SSH + pull/restart, or push image to a registry and redeploy)
- [ ] Deliberately break a test and push, to confirm the pipeline actually fails

**On track if:** the broken-test push genuinely fails the pipeline — don't just assume it works.

### Week 14 — Review, logging, documentation (buffer week)
- [ ] Add basic structured logging (Python's `logging` module, timestamps + levels)
- [ ] Write a 1–2 page architecture doc as if handing this project to a client
- [ ] Catch up anything from weeks 11–13 that slipped

**On track if:** you could walk a stranger through this project's architecture in under 5 minutes using only your doc.

---

## Phase 4: LLM & Agent Integration (Weeks 15–18)

### Week 15 — LLM API fundamentals
- [ ] Anthropic docs (docs.claude.com): Messages API, system prompts, multi-turn conversations
- [ ] Build a script that turns messy unstructured text (e.g. sample support emails) into structured JSON (sentiment, category, urgency)

**On track if:** the script reliably returns valid, parseable JSON across 10 different sample inputs.

### Week 16 — Tool use / function calling
- [ ] Anthropic docs: tool-use section
- [ ] Build a small agent that calls your Week 10 Weather Service and answers natural-language questions using the result

**On track if:** asking "will I need an umbrella in Toronto tomorrow" correctly triggers the tool call and produces a sensible answer.

### Week 17 — RAG basics
- [ ] Learn embeddings conceptually
- [ ] Generate embeddings via Voyage AI (free tier, Anthropic's recommended partner) or a local option like `sentence-transformers` — note: Anthropic's API itself has no embeddings endpoint
- [ ] Set up Chroma as a local vector store
- [ ] Build a "chat with your docs" mini-app over 5–10 of your own text/PDF files

**On track if:** you can ask a question you already know the answer to about your source docs and get a correct, grounded answer — not a plausible hallucination.

### Week 18 — Bring it together
- [ ] Add an LLM-powered feature to your Phase 2/3 project (auto-categorize tasks, summarize data, or natural-language Q&A over your Postgres data)

**On track if:** the feature works end-to-end in your *deployed* app, not just locally.

---

## Phase 5: Systems Design + Interview Prep (Weeks 19–22)

### Week 19 — System design fundamentals
- [ ] roadmap.sh system design guide, or *System Design Interview* by Alex Xu vol. 1, ch. 1–4

**On track if:** you can explain out loud vertical vs. horizontal scaling, and when you'd reach for a cache.

### Week 20 — Practice designing systems
- [ ] Design (out loud, 45–60 min timeboxed each): a URL shortener
- [ ] Design: a chat app
- [ ] Design: a notification system

**On track if:** each design covers a data model, an API shape, one bottleneck, and one way to scale past it.

### Week 21 — DS&A push
- [ ] NeetCode — Two Pointers category
- [ ] NeetCode — Sliding Window category
- [ ] NeetCode — Binary Search category
(prioritize whichever felt weakest back in Week 4)

**On track if:** cumulative NeetCode count is around 30–35 problems solved unaided.

### Week 22 — Mock interviews
- [ ] 2–3 mock technical interviews (Pramp, or a friend)
- [ ] 1–2 mock behavioral interviews focused on your SE→FDE narrative
- [ ] Rewrite resume bullets around your capstone + SE experience reframed as client-facing technical work

**On track if:** you can tell your "why FDE" story in under 90 seconds without rambling, and you've gotten specific feedback on one weak spot.

---

## Phase 6: Capstone + Job Search (Weeks 23–26)

### Weeks 23–24 — Capstone: simulate an actual FDE engagement
- [ ] Pick a deliberately ambiguous, client-style problem
- [ ] Build the full pipeline: ingest messy data → Postgres → FastAPI → React frontend → LLM feature → Dockerized → deployed → CI/CD
- [ ] Document it like a client handoff, not a tutorial project

**On track if:** a stranger could clone your repo, read your README, and understand what it does and why you built it that way — without asking you anything.

### Week 25 — Polish & publish
- [ ] Clean up GitHub (README quality > repo count now)
- [ ] Write a short case-study post about the capstone
- [ ] Update LinkedIn
- [ ] Send 10–15 applications

**On track if:** at least one piece of content is published and applications are actually sent, not just drafted.

### Week 26 — Applications + informational interviews
- [ ] Keep applying
- [ ] Reach out to 2–3 actual FDEs for informational conversations

**On track if:** at least one informational conversation is booked or completed.

---

## Notes on using your current job
- You already have the hardest-to-teach FDE skill: sitting with a client, understanding a vague ask, and translating it into something buildable. Don't undersell that in interviews.
- If Webflow has any internal API/integrations work, ask to shadow or contribute — real client context beats another side project.
- Webflow's own APIs are a legitimate, on-brand project source for Phase 2/4 — e.g. a tool that uses the Webflow API + an LLM to audit a client's site structure. That's a portfolio piece that's very on-the-nose for an FDE hiring manager.
