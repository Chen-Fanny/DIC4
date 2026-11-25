# Design: ICEIB 2027 Paper in A-to-Z Style

## Context

See `proposal.md` for motivation. The existing draft in `ICEIB paper/main.tex` (authored by Yi-Fan Chen, National Chung Hsing University) uses IEEEtran conference format and is grounded in `Food-Guardian/`, but currently splits Proposed Design across two separate sections (`System Architecture and Data Model` and `Core Algorithms and Safety Mechanisms`), separates `Limitations and Future Work` from `Conclusion`, and does not yet explicitly cover all 36 A-to-Z (`A2Z`) markers from `ref/A2Z_academic_writing_style.md` (such as the Article Summary Table in Related Work, numbered `(1)--(8)` architecture flow, standalone Agent Decision Flowchart, explicit Baseline 1/2 comparison framing, and worked walkthrough example `PJ`).

## Goals / Non-Goals

- **Goals**:
  - Consolidate the manuscript into the exact requested top-level sections: `Abstract`, `I. Introduction`, `II. Related Work`, `III. Proposed Design`, `IV. Experiment`, `V. Conclusion`, and `References`.
  - Map all 36 A-to-Z markers (`A--F`, `G--L`, `M--O`, `PA--PM`, `Q--V`, `W--Z`) into crisp academic prose, tables, TikZ diagrams, equations, and `Algorithm 1`.
  - Preserve 100% factual fidelity to `Food-Guardian/` (no fabricated waste-reduction percentages, no unexecuted test claims).
- **Non-Goals**:
  - Modifying any Python source code or test fixtures in `Food-Guardian/`.
  - Compiling a PDF in an environment lacking TeX (though the LaTeX will remain pure ASCII and `pdflatex`-clean).

## Decisions

1. **Section Consolidation (`Proposed Design` and `Conclusion`)**:
   - *Choice*: Merge `System Architecture and Data Model` + `Core Algorithms and Safety Mechanisms` into `III. Proposed Design` (with subsections `A` through `F` covering `PA--PM`), and integrate `Limitations and Future Work` into `V. Conclusion` (`W--Z`).
   - *Rationale*: Matches the user's requested top-level section list verbatim while preserving every technical formula, schema table, and algorithm.

2. **A-to-Z Structural Mapping**:
   - **Abstract (`A--F`)**: Single cohesive IEEE paragraph progressing smoothly through Attention Getter -> But -> Cure -> Development -> Experiments -> Findings.
   - **I. Introduction (`G--L`)**: General domain background (`G`), However challenges (`H`), In-literature context (`I`), Judgement of existing paradigms (`J`), Keypoint contributions (`K`), and List Organization (`L`).
   - **II. Related Work (`M--O`)**: `A. AI Technology Methods` and `B. Food-Domain Knowledge` (`M`), `C. Emerging Hybrid Paradigm` (`N`), and `D. Comparative Summary and Research Gap` (`O`) featuring **Table I** (Article Summary Table covering AI + Domain literature vs. Food Guardian) and **Table II** (SWOT / Capability Matrix), ending with the Research Gap logic chain.
   - **III. Proposed Design (`PA--PM`)**:
     - `A. Design Objectives and System Foundations (PA, PB, PC)`
     - `B. Numbered Eight-Step Domain AI Agent Architecture (PD, PE, PG)` with TikZ **Fig. 1** showing numbered `(1)` through `(8)` flow and **Table III** (Module Responsibility Matrix).
     - `C. Relational Schema and State Formulation (PF)` with **Table IV** (SQLite 3 schema).
     - `D. Agent Workflow Flowchart and Pseudocode (PH, PI)` with TikZ **Fig. 2** (Decision Flowchart) and **Algorithm 1** (line-numbered pseudocode).
     - `E. Mathematical Formulation and Safety Algorithms (PM, PK)` covering `Status(d, t)`, 3-tier safety triage, dimension-safe portion scaling, `coverage`, `urgency`, `score`, and `Waste Rate_u`.
     - `F. Worked Execution Walkthrough (PJ, PL)` tracing the 2-serving Tomato vs. Cabbage Scrambled Eggs and Chicken Breast safety check on the pinned `2026-11-11` fixture.
   - **IV. Experiment (`Q--V`)**:
     - `A. Evaluation Metrics and Baseline Design (Q, R)` defining Baseline 1 (Unranked/Random), Baseline 2 (Pure LLM without live tools), and Proposed Food Guardian (`balanced`, `ready_now`, `expiry_first`).
     - `B. Simulation Setup and Tuning Parameters (S, T)` documenting the 30-case v3.3 suite, `TODAY = 2026-11-11`, `temperature = 0.2`, `timeout = 35 s`, `recursion_limit = 18`, `max_retries = 1`, $t \in \{1,3,5,7\}$, weights $0.65 / 0.35$, and chunking $1200$ chars.
     - `C. Offline and Live Experimental Results (U, V)` with **Table V** (Offline v3.3: 25/25 PASS, 5 NOT_RUN) and **Table VI** (Live Gemini v3.3: 3/3 PASS, 1 retry, 11.710 s mean latency, explicit pending RAG/human review disclosures).
   - **V. Conclusion (`W--Z`)**: Synthesizes `W` (What Proposed), `X` (eXcel scope & boundaries), `Y` (Yields/repository deliverables), and `Z` (Zen/future directions).

3. **Pure ASCII & Standalone TikZ**:
   - *Choice*: Keep `ICEIB paper/main.tex` strictly ASCII and draw both the numbered architecture graph (`Fig. 1`) and agent flowchart (`Fig. 2`) in TikZ (`\resizebox{\columnwidth}{!}{...}`), keeping `table*` / `table` balanced to target 6--7 two-column IEEE pages (within ICEIB's 4--8 page limit).

## Risks / Trade-offs

- **Risk**: In the Article Summary Table (`Table I`), citing external papers without hallucinating fake bibliographic details -> *Mitigation*: Only cite real, verified works already in our bibliography (`yao2023react`, `lewis2020rag`, `tfda_date`, `foodsafety_4steps`, etc.) plus general category labels (`Prior Vision Prototypes`, `Rule-Based Date Trackers`) rather than inventing fake authors/years/numbers.
- **Risk**: Overly long two-column tables overflowing column margins -> *Mitigation*: Use `table*` with `\resizebox{\textwidth}{!}{...}` for wide multi-column summary tables and `tabular` with explicit `p{...}` columns for single-column tables.

