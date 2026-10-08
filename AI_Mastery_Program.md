# Practical AI Mastery — 6-Month Roadmap
### From quant engineer/strategist → practical AI builder
*Designed for ~45–60 min on weekdays, optional 1–1.5h deep-work block on one weekend day. Fully modular — pause/compress weeks freely around grad applications.*

---

## 0. How to use this program

**Principles:**
1. **Build > watch.** Every week ends with something you ran, broke, and fixed — not just a video finished.
2. **Learn AI by using AI.** Use ChatGPT/Claude/Copilot constantly while studying: ask them to re-explain, quiz you, review your code. This *is* the practical skill (prompt literacy), not cheating.
3. **Teach-back.** Every 2 weeks, write a 5-line LinkedIn/notion note summarizing what you built. Cheap personal-branding win for grad applications too.
4. **Build in public, in your existing repo.** Use your `coding-projects` GitHub repo (already on your Desktop) — create one subfolder `ai-mastery-journey/` inside it, with one sub-subfolder per week (`week-01/`, `week-02/`...). No new repo needed; by month 6 this folder *is* your portfolio.
5. **Compress, don't skip.** Busy week? Do only the "Fri hands-on" line. Never skip to "catch up later" — momentum > completeness.
6. **You already know the hard math.** We will NOT re-derive backprop or attention from scratch mathematically — you'll get the intuition + the practical API fast, and go deeper only where it pays off (e.g., understanding transformer attention, because it explains *why* prompting/RAG work the way they do).
7. **Papers are a bonus layer, not a requirement.** Each phase links 1-2 original papers tagged **Core** (directly explains what you're building that week — read these if you read any) or **Bonus** (cultural/historical context — skip freely if time is tight). None are required to progress; see the full track in section 9.

**Weekly time budget:** ~4–5h/week total (5 × 45–60min weekdays + 1 optional weekend session). That's it.

---

## 1. Program at a glance

| Phase | Weeks | Theme | You'll walk away able to... | Capstone artifact |
|---|---|---|---|---|
| 0 | Day 0 | Setup | Have a working AI dev environment | — |
| 1 | 1–4 | ML & Python foundations | Train/evaluate a classic ML model, know core vocabulary | Kaggle Titanic submission + mini NN |
| 2 | 5–8 | Deep Learning & NLP/Transformers | Understand *why* LLMs work, fine-tune a small model | Fine-tuned text classifier |
| 3 | 9–12 | LLMs, APIs & Prompt Engineering | Use LLM APIs like a pro, design reliable prompts | LLM-powered automation script |
| 4 | 13–16 | RAG & Vector Search | Build a "chat with your own data" app | Deployed RAG chatbot |
| 5 | 17–19 | Agents, Tool Use & Automation | Build multi-step autonomous agents | Research/automation agent |
| 6 | 20–24 | Full-stack AI product | Ship and deploy a real AI business tool | Deployed capstone product |

---

## 2. Day 0 — Setup checklist (~1h, one-time)

- [x] Install **Python 3.11+** and **VSCodium** (vscodium.com — open-source build of VS Code, no Microsoft telemetry/branding). Add the Python + Jupyter extensions from **Open VSX** (open-vsx.org, the open-source extension marketplace VSCodium uses instead of the MS Marketplace)
- [ ] In your existing `coding-projects` repo (already on your Desktop), create a new folder `ai-mastery-journey/` with a `README.md` as the index for this whole program — this is where all weekly work will live (no new repo)
- [ ] Create a **Google Colab** account (free GPU — colab.research.google.com)
- [ ] Create a **Kaggle** account (kaggle.com) — free notebooks + datasets + competitions
- [ ] Create a **Hugging Face** account (huggingface.co) — models, datasets, free Spaces hosting
- [ ] Get an **OpenAI API key** (platform.openai.com — pay-as-you-go, a few $ lasts the whole program) *and/or* an **Anthropic API key** (console.anthropic.com). Set a $5–10 hard spending cap.
- [ ] Install core libraries: `pip install numpy pandas scikit-learn matplotlib jupyter openai anthropic`
- [ ] 20-min read: *"AI landscape 2026 in plain English"* — ask ChatGPT/Claude directly: **"Explain the current AI landscape (ML vs DL vs LLMs vs agents) to an engineer-economist in 10 minutes, with a diagram in text."** (This doubles as your first real prompting exercise.)

---

## 3. Phase 1 — ML & Python Foundations (Weeks 1–4)

> Goal: speak fluent ML vocabulary and know what's happening "under the hood" before jumping to LLMs.

**Core resources for this phase:**
- Kaggle Learn (free, hands-on, ~2-4h per micro-course): *Python*, *Intro to Machine Learning*, *Intermediate Machine Learning*, *Pandas* → kaggle.com/learn
- Google Machine Learning Crash Course (free) → developers.google.com/machine-learning/crash-course
- 3Blue1Brown — *Neural Networks* series (YouTube, ~1h total, best visual intuition ever made)
- Andrew Ng, *Machine Learning Specialization* (Coursera — audit for free)

### Week 1 — Python for data/AI + ML vocabulary
- Mon: Numpy/Pandas refresher (you know Python already — speed-run Kaggle "Pandas" micro-course, ch.1-3)
- Tue: Pandas micro-course ch.4-6
- Wed: Kaggle "Intro to Machine Learning" ch.1-3 (what is a model, train/test split, decision trees)
- Thu: Kaggle "Intro to Machine Learning" ch.4-7 (underfitting/overfitting, random forests)
- Fri (hands-on): Finish the course's mini exercise, submit your first prediction to the Kaggle "Housing Prices" getting-started competition
- Weekend (optional): Explore the dataset yourself, try improving your score

### Week 2 — Supervised learning, deeper
- Mon: Regression vs classification, metrics (MSE, accuracy, precision/recall, ROC-AUC) — Google Crash Course modules
- Tue: scikit-learn in practice: `train_test_split`, `Pipeline`, `cross_val_score`
- Wed: Kaggle "Intermediate Machine Learning" ch.1-3 (missing values, categorical variables)
- Thu: Kaggle "Intermediate Machine Learning" ch.4-6 (pipelines, cross-validation, XGBoost)
- Fri (hands-on): Join the **Titanic** competition (kaggle.com/competitions/titanic), build your own pipeline end-to-end
- Weekend (optional): Try XGBoost, compare to your first model, write 5 lines on what changed your score

### Week 3 — From ML to Neural Networks (intuition)
- Mon: 3Blue1Brown ep.1 — "But what is a neural network?"
- Tue: 3Blue1Brown ep.2-3 — gradient descent & backpropagation (intuition only, you have the calculus already)
- Wed: Read: *"A visual intro to gradient descent"* + play with a loss-landscape visualizer (search "playground.tensorflow.org" — interactive, no install)
- Thu: scikit-learn `MLPClassifier` — train a tiny neural net on a dataset you already used (Titanic or digits)
- Fri (hands-on): Compare your NN vs your earlier Random Forest — same metrics, discuss why/when NNs win
- Weekend (optional): Write your "teach-back" note #1: ML in 10 bullet points, in your own words

### Week 4 — Consolidation + mini-project
- Mon-Thu (45min each): Pick ONE Kaggle "Getting Started" competition relevant to you (e.g. House Prices or a text one) and iterate: feature engineering, model comparison, submission
- Fri: Finalize submission, push full notebook to your GitHub repo with a README
- Weekend (optional): **Checkpoint quiz** — ask ChatGPT: *"Quiz me on ML fundamentals: overfitting, bias-variance, cross-validation, regularization, key metrics"* — redo any concept you fumble

✅ **End of Phase 1 checklist:** I can explain overfitting, I can build & evaluate a scikit-learn model pipeline, I have 1 Kaggle submission in my portfolio.

---

## 4. Phase 2 — Deep Learning & NLP/Transformers (Weeks 5–8)

> Goal: understand *why* LLMs behave the way they do — embeddings, attention, pretraining — and get hands-on with Hugging Face.

**Core resources:**
- Hugging Face **NLP Course** (free, excellent, code-first) → huggingface.co/learn/nlp-course
- Jay Alammar — *The Illustrated Transformer* & *The Illustrated GPT-2* (blog, ~30min each, THE classic explainer)
- Andrej Karpathy — *Neural Networks: Zero to Hero* (YouTube series, dip into "Let's build GPT from scratch" even just first 20 min for intuition)
- PyTorch *60-minute blitz* tutorial (pytorch.org/tutorials)

### Week 5 — Deep learning framework basics
- Mon-Tue: PyTorch 60-minute blitz (tensors, autograd) — just enough to read others' code comfortably
- Wed: Hugging Face NLP Course ch.1 (what is NLP, pipelines)
- Thu: Hugging Face NLP Course ch.2 (tokenizers, models, "Behind the pipeline")
- Fri (hands-on): Run 3 different `pipeline()` tasks in a Colab notebook (sentiment analysis, summarization, translation) on your own text
- Weekend (optional): Try it on something real — e.g. summarize a case study or lecture PDF

### Week 6 — Embeddings & representation
- Mon: What are embeddings — intuition (words/sentences → vectors), watch a short explainer video (search "vector embeddings explained simply")
- Tue: Hugging Face NLP Course ch.3 (fine-tuning a pretrained model, part 1)
- Wed: HF NLP Course ch.3 (part 2 — full training loop)
- Thu: Try `sentence-transformers` library — embed sentences, compute cosine similarity between business/finance sentences
- Fri (hands-on): Mini demo notebook: given 5 customer reviews, embed them and cluster/find the most similar pair
- Weekend (optional): Teach-back note #2: "Embeddings in plain English, with my own example"

### Week 7 — Attention & Transformers (the "aha" week)
- Mon: *The Illustrated Transformer* (read slowly, it's the single best hour you'll spend this program)
- Tue: *The Illustrated GPT-2* (how decoder-only models generate text)
- Wed: Watch Karpathy's "State of GPT" talk (YouTube, ~45min, watch in 2 sittings) — how models are actually trained (pretrain → SFT → RLHF)
- Thu: Re-read your notes, ask Claude/ChatGPT: *"I just learned about self-attention — quiz me and poke holes in my understanding"*
- Fri (hands-on): Diagram (by hand or in Mermaid) the flow: tokens → embeddings → attention → output. Save it to your repo.
- Weekend (optional): No new content — consolidate, re-watch anything fuzzy

### Week 8 — Fine-tuning practice (mini-project)
- Mon-Wed (45min each): HF NLP Course ch.4-5 (sharing models, datasets library) + prep a small custom dataset (e.g. labelled tweets/reviews, or synthesize one with ChatGPT)
- Thu: Fine-tune **DistilBERT** on your dataset in Colab (free GPU) for a classification task (sentiment, topic, or spam/ham)
- Fri (hands-on): Evaluate it, push the model card to Hugging Face Hub (free), write a short README
- Weekend (optional): Teach-back note #3 + tidy up GitHub repo

✅ **End of Phase 2 checklist:** I can explain attention/transformers at an intuitive level, I've fine-tuned and shared a real model.

---

## 5. Phase 3 — LLMs, APIs & Prompt Engineering (Weeks 9–12)

> Goal: become genuinely excellent at using LLMs via API — the single highest-leverage practical skill for both work and business tools.

**Core resources:**
- **Prompt Engineering Guide** → promptingguide.ai (the reference)
- DeepLearning.AI short course: *"ChatGPT Prompt Engineering for Developers"* (free, ~1.5h) → deeplearning.ai/short-courses
- DeepLearning.AI short course: *"Building Systems with the ChatGPT API"* (free)
- **OpenAI Cookbook** (github.com/openai/openai-cookbook) — real code recipes
- Anthropic's prompt engineering docs (docs.anthropic.com)

### Week 9 — How LLMs really behave
- Mon: Re-watch/skim Karpathy "State of GPT" notes — focus on instruction-tuning & RLHF this time
- Tue: Read OpenAI & Anthropic model docs on capabilities/limits (context windows, hallucination, knowledge cutoff)
- Wed: Experiment manually in ChatGPT/Claude web UI: test same prompt 5 ways, observe variance
- Thu: Read: "temperature, top-p, system prompts" explainer (search official OpenAI API docs — "Chat Completions guide")
- Fri (hands-on): Write your first Python script calling the OpenAI/Anthropic API (`pip install openai`), print a response
- Weekend (optional): Try the same call with different temperature/system prompt settings, log outputs

### Week 10 — Prompt engineering techniques
- Mon: Prompting Guide — zero-shot, few-shot, basic techniques
- Tue: Prompting Guide — chain-of-thought, self-consistency
- Wed: DeepLearning.AI "ChatGPT Prompt Engineering for Developers" part 1
- Thu: Same course, part 2 (summarizing, inferring, transforming text)
- Fri (hands-on): Build a reusable **prompt template library** (Python dict/functions) for 5 tasks you do often (summarize, draft email, extract data, classify, explain)
- Weekend (optional): Apply it to something real this week (e.g. summarize a long reading for one of your courses)

### Week 11 — Structured outputs & API mastery
- Mon: Structured outputs / JSON mode / function calling concept (OpenAI docs)
- Tue: OpenAI Cookbook — pick 2 recipes to run yourself (e.g. "How to format inputs to ChatGPT models", "Function calling")
- Wed: Build a script that extracts structured data (JSON) from messy text (e.g. parse unstructured meeting notes into {attendees, decisions, action_items})
- Thu: Error handling, retries, cost/token awareness (`tiktoken` to count tokens before calling)
- Fri (hands-on): Package the above into a small reusable Python module with proper error handling
- Weekend (optional): Teach-back note #4: "5 prompting tricks I now use daily"

### Week 12 — Mini-project: LLM-powered automation tool
- Mon-Thu (45min each): Build a CLI/script that solves a **real recurring task of yours** — options:
  - Extend your existing Python/VBA automation app with a natural-language interface (e.g. "summarize this Excel sheet in English")
  - A PDF/lecture-notes summarizer + flashcard generator (useful for your own courses!)
  - A job-application assistant: tailor a CV bullet list / draft a cover letter from a job description + your CV
- Fri: Polish, add a README, push to GitHub
- Weekend (optional): Use the tool for real on an actual task you have this week

✅ **End of Phase 3 checklist:** I can call LLM APIs confidently, write reliable prompts, extract structured data, and I have one real working automation tool.

---

## 6. Phase 4 — RAG & Vector Search (Weeks 13–16)

> Goal: build apps that answer questions over *your own* documents — the #1 practical business use case for LLMs.

**Core resources:**
- DeepLearning.AI: *"Building and Evaluating Advanced RAG"*, *"LangChain Chat with Your Data"* (free short courses)
- LangChain docs & tutorials (python.langchain.com) — or LlamaIndex (docs.llamaindex.ai), pick one
- Chroma (docs.trychroma.com) — free local vector database
- Streamlit docs (docs.streamlit.io) — fastest way to build an AI web UI in Python

### Week 13 — Vector search fundamentals
- Mon: Recap embeddings (you've seen this in Wk6) + concept of vector similarity search / nearest neighbors
- Tue: Read intro to vector databases — why/when RAG beats "stuff everything in the prompt" or fine-tuning
- Wed: Set up **Chroma** locally, embed and store 10 sample documents
- Thu: Query it, inspect what gets retrieved vs not — try to break it with ambiguous queries
- Fri (hands-on): Script: given a folder of .txt files, embed & store them all in Chroma
- Weekend (optional): Try it on your own lecture notes/readings folder

### Week 14 — RAG pipeline
- Mon: DeepLearning.AI "LangChain Chat with Your Data" part 1
- Tue: Same course, part 2 — retrieval strategies, chunking choices
- Wed: Build a basic RAG chain: retrieve chunks → stuff into prompt → LLM answers with citations
- Thu: Experiment with chunk size/overlap, observe answer quality changes
- Fri (hands-on): Add source citation to your RAG answers (show which chunk/doc was used)
- Weekend (optional): Teach-back note #5: "How RAG actually works, explained simply"

### Week 15 — Build the app
- Mon: Streamlit basics (input box, chat UI components) — docs + a 20-min tutorial
- Tue: Wire your RAG pipeline into a Streamlit chat interface
- Wed: Add file upload (let user drop their own PDFs in)
- Thu: Polish UX: loading states, error handling, "no answer found" cases
- Fri (hands-on): End-to-end test with a real document set (e.g. your MSc course readings or a company's annual report)
- Weekend (optional): Ask a friend/classmate to try it and give feedback

### Week 16 — Evaluation & deployment
- Mon: DeepLearning.AI "Building and Evaluating Advanced RAG" — evaluation metrics for RAG (faithfulness, relevance)
- Tue: Add a few hand-written test questions + expected answers, check your pipeline against them
- Wed: Deploy to **Hugging Face Spaces** (free hosting for Streamlit/Gradio apps)
- Thu: Fix deployment issues, add a clean README + screenshot
- Fri (hands-on): Share the live link, write a short LinkedIn/portfolio post about it
- Weekend (optional): Rest, or polish UI further

✅ **End of Phase 4 checklist:** I have a deployed, working "chat with your documents" app I can demo live.

---

## 7. Phase 5 — Agents, Tool Use & Automation (Weeks 17–19)

> Goal: build systems that take multi-step actions, not just answer questions — this is where AI becomes a true productivity/business multiplier.

**Core resources:**
- Hugging Face **Agents Course** (free) → huggingface.co/learn/agents-course
- DeepLearning.AI: *"Functions, Tools and Agents with LangChain"* (free)
- LangChain "agents" docs/tutorials
- n8n (n8n.io, free self-hosted) or Zapier AI actions — for no-code/low-code AI automation

### Week 17 — Tool use & function calling
- Mon: Concept: function/tool calling — letting the LLM "decide" to call a Python function (e.g. a calculator, a web search)
- Tue: OpenAI/Anthropic docs on tool use — implement one tool call yourself (e.g. a calculator or a weather/stock-price lookup function)
- Wed: Hugging Face Agents Course unit 1
- Thu: HF Agents Course unit 2 (ReAct pattern — reason + act loop)
- Fri (hands-on): Build an agent with 2 tools (e.g. web search + calculator) that answers a multi-step question
- Weekend (optional): Stress-test it with tricky multi-hop questions

### Week 18 — Multi-step agent project
- Mon-Thu (45min each): Build a **research/automation agent** for a real use case, e.g.:
  - A "market/competitor research assistant": given a company name, search, summarize, output a mini brief
  - A "meeting-prep agent": given a company + role, gather public info and draft talking points (useful for your own interviews!)
  - Extend Week 12's automation tool into an agent that decides *which* action to take
- Fri: Test, debug, refine the loop (agents fail a lot — this is normal, debugging IS the skill)
- Weekend (optional): Try it on a real upcoming interview/case study prep

### Week 19 — Reliability, guardrails & no-code automation
- Mon: Read about common agent failure modes (infinite loops, hallucinated tool calls) and mitigation (max steps, validation)
- Tue: Add basic guardrails/logging to your agent
- Wed: Explore **n8n** or Zapier AI — build one simple no-code automation (e.g. "new email → AI summary → Notion/Slack")
- Thu: Compare: when would you use code (LangChain) vs no-code (n8n/Zapier) in a real business context? Write 5 lines.
- Fri (hands-on): Finalize agent project, push to GitHub with README + demo GIF/video
- Weekend (optional): Teach-back note #6: "What I'd actually use agents for in a business"

✅ **End of Phase 5 checklist:** I've built and debugged a working multi-step agent, and I understand code vs no-code automation trade-offs.

---

## 8. Phase 6 — Full-Stack AI Product / Capstone (Weeks 20–24)

> Goal: ship one polished, deployed, end-to-end AI product that combines everything — and doubles as a genuine business/portfolio asset.

**Suggested capstone ideas (pick one, or bring your own — bonus points if it solves a real problem you have):**
- **AI Application Copilot**: upload CV + job description → tailored CV bullets, cover letter draft, likely interview questions + model answers (directly useful for your grad program search!)
- **AI Strategy Analyst**: upload a company's public filings/annual report → SWOT, key risks, auto-generated exec summary, chat Q&A (nice bridge to your Econ & Strategy MSc)
- **Smart Automation Hub**: evolve your original Python/VBA app into a web tool: natural-language → spreadsheet/data actions, with agent-based multi-step automations
- **Study Copilot**: a RAG + agent tool over all your MSc course materials (readings, slides) with quizzing and summarization

### Week 20 — Define & design
- Mon: Pick your capstone, write a 1-page spec (problem, user, core features, "done" criteria) — treat this like a mini business case (your strategy training shines here)
- Tue: Sketch architecture: data flow (frontend → backend → LLM/RAG/agent → response)
- Wed: Set up repo structure, choose stack (FastAPI backend + Streamlit, or FastAPI + simple HTML/CSS/JS frontend using your existing web skills)
- Thu: Build data layer (document ingestion / CV parsing / data loading depending on project)
- Fri (hands-on): Have a skeleton running end-to-end with dummy responses
- Weekend (optional): Gather/prepare real sample data to use throughout

### Week 21 — Backend build
- Mon: FastAPI basics (routes, request/response models) — docs tutorial, 30 min
- Tue: Wire your LLM/RAG/agent logic from Phases 3-5 into FastAPI endpoints
- Wed: Add structured outputs, error handling, logging
- Thu: Write 3-5 test cases, fix bugs
- Fri (hands-on): Backend fully functional via API calls (test with `curl`/Postman/Python requests)
- Weekend (optional): Buffer/catch-up

### Week 22 — Frontend build
- Mon: Choose Streamlit (fast) or HTML/CSS/JS (more control, leverages your existing skills) and scaffold the UI
- Tue: Connect frontend to backend API
- Wed: Build the core interaction loop (upload/input → processing state → result display)
- Thu: Polish UX — this is often what makes a demo land well with recruiters/users
- Fri (hands-on): Full end-to-end demo working locally
- Weekend (optional): Get a friend to test it, collect feedback

### Week 23 — Deployment & hardening
- Mon: Choose deployment target: Hugging Face Spaces (easiest for Streamlit/Gradio), or Render/Vercel free tier (FastAPI + static frontend)
- Tue: Deploy backend, fix environment/config issues
- Wed: Deploy frontend, connect to live backend, test publicly
- Thu: Add basic cost/rate-limit protection (cap tokens, handle API errors gracefully) — important if you share the link publicly
- Fri (hands-on): Final working public demo link
- Weekend (optional): Record a 2-min screen-capture demo video

### Week 24 — Present, reflect, plan next steps
- Mon: Write a proper README (problem, architecture diagram, tech stack, how to run, screenshots)
- Tue: Write a LinkedIn/portfolio post: what you built, what you learned, link to demo + repo
- Wed: Self-assessment: redo the Phase 1-5 checklists honestly, note any gaps
- Thu: Ask ChatGPT/Claude for a mock technical interview on AI fundamentals — identify weak spots
- Fri: Decide your next specialization track (see section 10 below)
- Weekend: Celebrate — you've gone from fundamentals to a deployed AI product in 6 months of ~45min/day 🎉

✅ **End of Phase 6 checklist:** I have one deployed, documented, demo-able AI product that I can discuss confidently in interviews or show to a business stakeholder.

---

## 9. Papers track — the scholarly/cultural layer (bonus, phase-aligned)

> Entirely optional, never blocking. Read **Core** papers only during the phase listed (they directly explain the mechanism you're building that week — reading them *then* turns them from abstract into obvious). Read **Bonus** papers whenever curiosity strikes, purely for the historical/cultural picture of how the field got here. Skim with an LLM alongside you: paste a dense section and ask *"explain this paragraph simply, then tell me why it mattered historically."*

| When | Paper | Tag | Why read it then |
|---|---|---|---|
| Day 0 / anytime | Turing, *"Computing Machinery and Intelligence"* (1950) | Bonus | The founding question of the whole field ("Can machines think?") — short, readable, no math |
| Phase 1 (Wk 1-4) | McCarthy et al., *Dartmouth Summer Research Project proposal* (1956) | Bonus | Where the term "Artificial Intelligence" was coined — 2-page read, fun historical anchor |
| Phase 2 (Wk 7) | Vaswani et al., *"Attention Is All You Need"* (2017) | **Core** | The Transformer paper — read right after *The Illustrated Transformer* in Wk 7, once the diagram already makes sense, so the equations click instead of intimidate |
| Phase 2 (Wk 7-8) | Devlin et al., *"BERT: Pre-training of Deep Bidirectional Transformers"* (2018) | Bonus | You're fine-tuning a BERT-family model in Wk 8 — skim the abstract + intro to know what you're actually using |
| Phase 3 (Wk 9) | Brown et al., *"Language Models are Few-Shot Learners"* (GPT-3, 2020) | **Core** | Explains *why* few-shot prompting (Wk 10) works at all — the paper that justified prompting as a technique |
| Phase 3 (Wk 9-10) | Ouyang et al., *"Training language models to follow instructions with human feedback"* (InstructGPT/RLHF, 2022) | **Core** | Explains instruction-tuning & RLHF — the gap between "raw LLM" and "ChatGPT-like assistant" you're calling via API |
| Phase 3 (Wk 10) | Wei et al., *"Chain-of-Thought Prompting Elicits Reasoning in Large Language Models"* (2022) | **Core** | Read right when you hit chain-of-thought in the Prompting Guide — primary source for a technique you'll use constantly |
| Phase 4 (Wk 13-14) | Lewis et al., *"Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks"* (2020) | **Core** | The RAG paper itself — read while building your first retrieval pipeline, it's short and maps 1:1 to what you're coding |
| Phase 5 (Wk 17-18) | Yao et al., *"ReAct: Synergizing Reasoning and Acting in Language Models"* (2022) | **Core** | The reasoning+acting loop you implement in your agent — read alongside the HF Agents Course unit on ReAct |
| Phase 6 / anytime after | LeCun, Bengio & Hinton, *"Deep Learning"* (Nature review, 2015) | Bonus | A field-defining review by the "godfathers of deep learning" — good capstone-era culture read, ties the whole program together |

**How to find them:** all are free — search the title on **arxiv.org** or **Google Scholar**; most have an accompanying blog explainer (search *"\[paper name\] explained"*) if you want a gentler on-ramp before the PDF.

---

## 10. Ongoing habits (run in parallel the whole program, ~10 min/week)

- **Newsletter**: *The Batch* by DeepLearning.AI (weekly, concise, high-quality) → deeplearning.ai/the-batch
- **Community**: Kaggle forums, Hugging Face forums — skim when stuck, not for browsing
- **Build in public**: short posts every 2 weeks (teach-back notes above) — compounds into a visible portfolio by month 6, genuinely useful for grad program / job applications
- **Keep a "prompt library" file**: every good prompt you write, save it — becomes your personal toolkit

---

## 11. Resource cheat-sheet (all in one place)

**Interactive / courses (all free):**
- kaggle.com/learn — Python, Intro/Intermediate ML, Pandas
- developers.google.com/machine-learning/crash-course
- huggingface.co/learn/nlp-course
- huggingface.co/learn/agents-course
- deeplearning.ai/short-courses — Prompt Engineering, Building Systems w/ ChatGPT API, LangChain (x2), Advanced RAG, Functions/Tools/Agents w/ LangChain
- course.fast.ai — optional deep-dive if you want more DL after Phase 2
- coursera.org/specializations/machine-learning-introduction (audit for free) — optional alternative/complement to Phase 1

**Reference docs & guides:**
- promptingguide.ai
- cookbook.openai.com
- docs.anthropic.com
- python.langchain.com / docs.llamaindex.ai
- docs.trychroma.com
- docs.streamlit.io / gradio.app
- fastapi.tiangolo.com
- huggingface.co/spaces (free deployment)

**Best single explainers (bookmark these):**
- 3Blue1Brown — "Neural Networks" YouTube series
- Jay Alammar — *The Illustrated Transformer*, *The Illustrated GPT-2*
- Andrej Karpathy — "State of GPT" talk, "Neural Networks: Zero to Hero" series
- playground.tensorflow.org — interactive neural net visualizer

**Practice grounds:**
- kaggle.com/competitions (Getting Started competitions: Titanic, House Prices)
- huggingface.co/models & datasets (browse, reuse)
- Your own repo: `coding-projects/ai-mastery-journey/`

---

## 12. After month 6: specialization menu

Once the core practical loop is solid, pick based on what excites you / your career direction:
- **AI for business/strategy**: AI use-case evaluation, build-vs-buy frameworks, LLMOps cost modeling — pairs perfectly with your MSc
- **MLOps/deployment depth**: Docker, cloud (AWS/GCP free tiers), monitoring, CI/CD for AI apps
- **Advanced fine-tuning**: LoRA/QLoRA, DeepLearning.AI "Finetuning Large Language Models" short course
- **Multi-agent systems**: CrewAI, AutoGen — orchestrating teams of agents
- **Computer vision / multimodal**: if a use case pulls you there

---

### Final note
Every single resource above is free. The only real cost is a few dollars of LLM API usage (cap it at $10-15 for the whole program) and your ~5 hours/week. The structure is intentionally modular — if a week gets eaten by grad applications, just do the Friday hands-on line and move on. Consistency across 24 weeks beats intensity across 2.
