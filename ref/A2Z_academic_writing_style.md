# A-to-Z (A2Z) Academic Writing Style Reference (SOP)

Extracted from `Food-Guardian/系統設計提案解析.pdf` (*A-Z SOP 標準學術論文架構規範 / A2Z Outline Standard Operating Procedure*) and mapped to IEEE ICEIB conference paper sections.

## Section Mapping Overview

| Paper Section | A-Z Codes | Count | Core Purpose |
|---|---|---:|---|
| **Abstract** | A -- F | 6 | 6-part concise summary from motivation to verified findings |
| **Introduction** | G -- L | 6 | Background, research gap, literature context, SWOT/judgement, contributions, paper outline |
| **Related Work** | M -- O | 3 | Method taxonomy (1/2 AI + 1/2 Domain), new proposed trend, Article Summary Table & SWOT |
| **Proposed Design** | PA -- PM | 13 | System aim, architecture graph (numbered flow), formulation, Flowchart + Algorithm Pseudocode, math proof |
| **Experiment** | Q -- V | 6 | Evaluation metrics, baseline comparison, testbed setup, tuning parameters, results, verification |
| **Conclusion** | W -- Z | 4 | Recap of proposed solution, scope/strengths, deliverables, future work |
| **References** | -- | -- | IEEE numbered bibliography (`[1]`, `[2]`, ...) |

---

## Detailed 36-Marker Checklist

### 1. Abstract (A--F)
- **A. Attention Getter**: Open with concrete household food waste context and authoritative statistics.
- **B. But (Challenge)**: State the core limitation of existing approaches and the Research Gap (e.g., standalone chatbots lack live inventory grounding, atomic deduction, and expiry-aware prioritization).
- **C. Cure**: Introduce the proposed solution (**Food Guardian**: knowledge-guided domain AI agent integrating SQLite transaction safety, deterministic services, RAG, and LLM tool calling).
- **D. Development**: Summarize the layered methodology (Streamlit + Python Services + SQLite + LangGraph/Gemini + ChromaDB RAG).
- **E. Experiments**: State the evaluation setup, dataset/cases, baselines, and metrics (30-case v3.3 suite, offline deterministic checks, live multi-tool trace accuracy).
- **F. Findings**: Report observed verified results honestly (25/25 offline checks passed; 3/3 non-RAG live multi-tool cases achieved 100% valid tool selection in 11.71 s mean latency; pending RAG live & human quality review).

### 2. Introduction (G--L)
- **G. General**: Domain background and real-world household scenario.
- **H. However**: Deepen the technical/domain challenges (inventory blindness, Use By vs. Best Before confusion, actionability gap).
- **I. In literature**: Briefly survey 3--5 relevant solution directions in prior literature.
- **J. Judgement**: Evaluate strengths and weaknesses of existing methods (pure LLM, manual apps, vision-only trackers vs. Food Guardian).
- **K. Keypoint**: Clearly itemize Novelty & Contributions (3--4 concrete technical contributions).
- **L. List Organization**: Provide a roadmap paragraph outlining the remaining sections of the paper.

### 3. Related Work (M--O)
- **M. Methods**: Categorize related research equally across **AI Technology** (LLM Tool Calling, ReAct/LangGraph, RAG) and **Domain Know-how** (food preservation, Use By vs. Best Before, safety guidelines).
- **N. New Proposed**: Highlight the emerging hybrid paradigm combining deterministic domain rule filtering with LLM natural-language reasoning.
- **O. Organize**: Present a structured **Article Summary Table** (`Ref. / Year / Problem / AI Method / Domain Knowledge / Dataset / Findings / Limitation`) and a comparative **SWOT / capability matrix**, culminating in the logic chain:
  $$\text{Existing Research} \longrightarrow \text{Limitations} \longrightarrow \text{Research Gap} \longrightarrow \text{Food Guardian}$$

### 4. Proposed Design (PA--PM)
- **PA. Aim**: Formal system objective statement (functional goals FR-01--FR-10 grounded in the codebase).
- **PB. Based on / Benefit**: Infrastructure foundation (Python, Streamlit, SQLite, LangGraph, ChromaDB) and architectural benefits.
- **PC. Cure / Cause**: Core mechanisms overcoming root causes (e.g., `BEGIN IMMEDIATE` + `Decimal` preventing over-deduction; three-tier safety triage preventing unsafe recommendations; dimension-safe scaling).
- **PD. Design**: Layered system architecture and numbered 8-step Domain AI Agent workflow (`(1) User Scenario -> (2) Query/Input -> (3) Planner & Agent -> (4) Data Acquisition -> (5) Analytics/Portion Engine -> (6) Domain Knowledge/Safety Integration -> (7) Decision/Recommendation -> (8) Output & Interaction`).
- **PE. Paper Element**: Component responsibility table mapping source modules (`src/ui/`, `src/agent/`, `src/services/`, `src/database/`) to roles.
- **PF. Formulation**: Data model & relational SQLite schema definitions (`inventory_items`, `consumption_waste_logs`, `recipe_recommendations`) and state lifecycle transitions.
- **PG. Graph**: Numbered system architecture diagram featuring steps `(1)` through `(8)`.
- **PH. How**: Step-by-step operational execution details of inventory, reminder, portion, safety, and RAG pipelines.
- **PI. Implementation**: Both an **Agent Decision Flowchart** and **Line-Numbered Pseudocode (`Algorithm 1`)**.
- **PJ. Jump to Example**: Concrete worked execution walkthrough (e.g., 2-serving Tomato Scrambled Eggs vs. Cabbage Scrambled Eggs under `ready_now` and `expiry_first` modes, and Chicken Breast safety validation).
- **PK. Keypoint Contribution**: Summary of core algorithmic and engineering safeguards.
- **PL. Later Simulation**: Verification matrix covering offline deterministic modules, static RAG metadata, and live multi-tool trace validation.
- **PM. Math Proof**: Formal mathematical definitions for calendar-day difference $d$, reminder status, inventory coverage, urgency score, composite score, and unit-isolated waste rate.

### 5. Experiment (Q--V)
- **Q. Quality & Quantity**: Formal evaluation metrics (offline pass rate, API Success Rate, Valid Tool Selection Accuracy, retry count, latency, and pending human review dimensions).
- **R. Related Compare**: Baseline comparison design (Baseline 1: Random/Unranked; Baseline 2: Pure LLM without inventory/safety tools; Proposed: Food Guardian `balanced` / `ready_now` / `expiry_first` + deterministic guards).
- **S. Simulation Setup**: Runtime environment, pinned reference date (`2026-11-11`), 6-item fixture inventory, 6-recipe sample set, and 30-case benchmark (`evaluation/cases.json`).
- **T. Tuning Parameters**: Explicit hyperparameters and thresholds ($\text{temperature}=0.2$, `timeout=35 s`, `recursion_limit=18`, `max_retries=1`, $t \in \{1,3,5,7\}$ days, weights $0.65 / 0.35$, chunk size $1200$ chars).
- **U. Useful Results**: Recorded quantitative tables (`offline_results.csv` 25/25 PASS, `live_results.csv` 3/3 PASS) and UI/system verification evidence.
- **V. Verify**: Validity discussion, explicit separation of API errors from tool-selection accuracy, and boundary/limitation honesty (pending live RAG `MUL-02`/`MUL-04` and human groundedness review).

### 6. Conclusion (W--Z)
- **W. What Proposed**: Concise recap of motivation and the Food Guardian domain AI agent architecture.
- **X. eXcel**: Clear scope boundaries and core strengths (local household inventory + transaction-safe deterministic tools + attributed knowledge).
- **Y. Yields**: Reproducible project deliverables (GitHub repository, `README.md`, `DESIGN.md`, `tests/`, `evaluation/`, `.env.example`, `requirements.txt`).
- **Z. Zen**: Future directions (larger curated recipe datasets, multi-dish shared-stock solver, live RAG/human audits, OCR/IoT assisted input, longitudinal household waste trials).

