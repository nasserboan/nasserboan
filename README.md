<h1 align="center"><code>nasserboan</code> — deployed to production since 2015</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1200&color=3FB950&center=true&vCenter=true&width=560&lines=Senior+ML+%2F+AI+Engineer;Deterministic+first%2C+LLM+as+fallback;I+ship+models%2C+not+notebooks;Homelab+status%3A+operational" alt="what I do" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-operational-3FB950?style=flat-square&logo=kubernetes&logoColor=white" alt="status" />
  <img src="https://img.shields.io/badge/location-Brasília,%20Brazil-30363D?style=flat-square" alt="location" />
  <img src="https://img.shields.io/badge/uptime-since%202015-30363D?style=flat-square&logo=github&logoColor=white" alt="uptime" />
  <img src="https://komarev.com/ghpvc/?username=nasserboan&label=requests&color=3FB950&style=flat-square" alt="views" />
</p>

> I build systems that reason over data and survive contact with production.
> Started in models, moved to infrastructure, ended up teaching machines to think —
> and I still reach for a parser before I reach for an LLM.

---

## `pipeline.dag` — how I got here

```mermaid
flowchart LR
    DS["Data Science<br/>2020–2023"] -->|scale it| MLOps["MLOps<br/>2023–2025"]
    MLOps -->|make it reason| AI["AI Engineering<br/>2025–2026"]
    style DS fill:#1f6feb,stroke:#1f6feb,color:#fff
    style MLOps fill:#8957e5,stroke:#8957e5,color:#fff
    style AI fill:#3fb950,stroke:#3fb950,color:#fff
```

**Data Science** taught me rigor — temporal splits, skew, the difference between a good metric and a lucky one. The model, it turned out, was 10% of the job; the pipeline was the rest. **MLOps** taught me to own that rest — the plumbing that feeds, monitors, and retrains a model long after training. **AI Engineering** taught me restraint: language models rewrote the rulebook, but an LLM is a tool, not a default — so I stopped reaching for one when a deterministic path will do.

---

## `self.yaml`

```yaml
service:
  name: nasserboan
  role: Senior ML / AI Engineer
  location: Brasília, Brazil 🇧🇷
  github_since: 2015
  ships_to_prod: true

capabilities:
  - LLMs, agents & Retrieval-Augmented Generation
  - Data lineage & metadata extraction
  - MLOps — Kubernetes, ArgoCD, GitOps, experiment tracking
  - End-to-end ML — feature engineering → serving
  - Community — talks & teaching

stack:
  languages:     [Python, SQL, Bash]
  ai_llm:        [LangChain, CrewAI, Ollama, OpenAI, ChromaDB, docling, MCP]
  ml:            [LightGBM, PyTorch, TensorFlow, scikit-learn, Optuna]
  serving:       [FastAPI, MongoDB, uv, Docker]
  orchestration: [Kubernetes, Minikube, ArgoCD, MLflow, Metaflow]
  frontend:      [React, Vite, Next.js]

contact:
  linkedin: nsboan
  email: nasserboan@gmail.com

party_trick: can bend his own ear   # load-bearing personality trait
```

---

## `services/` — running in production

### 🔗 Lineage — SQL data lineage as a service
FastAPI service that extracts table & column lineage from SQL and emits it to **OpenMetadata**. The design is the point: a deterministic **SQLGlot** parser handles the common case, and a **CrewAI + Ollama** agent only wakes up when the parser can't infer the relationship.

```mermaid
flowchart TD
    Q["SQL query"] --> P["SQLGlot parser<br/>deterministic and cheap"]
    P -->|parsed| G["Lineage graph"]
    P -->|no match| A["CrewAI + Ollama<br/>agent fallback"]
    A --> G
    G --> OM["OpenMetadata catalog"]
    style P fill:#3fb950,stroke:#2ea043,color:#fff
    style A fill:#d29922,stroke:#bb8009,color:#fff
    style G fill:#1f6feb,stroke:#1158c7,color:#fff
```

### 🤖 Finance RAG — documents in, answers out
Full stack, end to end: **FastAPI + MongoDB + Next.js**. PDFs parsed to markdown with `docling`, chunked and embedded into **ChromaDB**, retrieved by a **LangChain** agent. Ingestion runs as a DAG; the whole thing ships on Docker Compose.

### 🌾 agri-curve — MLOps on GitOps rails
Reproducible ML on **Kubernetes (Minikube) + ArgoCD**. Every experiment and hyperparameter declared as code, `kubectl`-driven pipelines, volume-mounted data.

### 🚴 bike-sharing — the craft, kept sharp
Classic-ML discipline with **LightGBM**: RMSLE from **0.32 → 0.28** through careful temporal splits and right-skew handling. Proof that the fundamentals didn't leave when the LLMs arrived.

### 📡 mcp-omd · mcp-poc — Model Context Protocol servers
Teaching LLMs to talk to my tools instead of the other way around.

---

## `observability/`

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=nasserboan&show_icons=true&hide_border=true&bg_color=0d1117&title_color=3fb950&icon_color=3fb950&text_color=c9d1d9" alt="stats" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=nasserboan&layout=compact&hide_border=true&bg_color=0d1117&title_color=3fb950&text_color=c9d1d9" alt="top langs" />
</p>

```yaml
talks_and_teaching:
  - PyData Brasília — MLflow for experiment tracking
  - Banco do Brasil — RAG systems in production
  - Ministério da Infraestrutura — taught Python
also_running:
  - a homelab that is somehow always on fire and always up
```

---

## `contact/`

<p align="center">
  <a href="https://www.linkedin.com/in/nsboan/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:nasserboan@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://github.com/nasserboan"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
</p>

<p align="center"><sub><code>$ uptime</code> → deployed since 2015 · no critical incidents · ship it 🚀</sub></p>
