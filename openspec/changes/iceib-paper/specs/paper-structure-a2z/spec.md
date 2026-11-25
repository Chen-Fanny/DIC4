# Spec Delta

## Purpose

Defines the required academic paper section structure and 36-marker A-to-Z (A2Z) writing standard for the Food Guardian ICEIB 2027 manuscript, grounded strictly in implemented repository evidence.

## ADDED Requirements

### Requirement: Required Top-Level Paper Sections
The manuscript MUST organize its body into the exact sequence: Abstract, Introduction, Related Work, Proposed Design, Experiment, Conclusion, and References.

#### Scenario: Section sequence verification
- **WHEN** the manuscript source in `ICEIB paper/main.tex` is inspected
- **THEN** it SHALL contain `abstract` followed by numbered sections titled `Introduction`, `Related Work`, `Proposed Design`, `Experiment`, `Conclusion`, and `thebibliography` (`References`)

### Requirement: Abstract Follows A-F Six-Part Structure
The Abstract MUST cover all six A-to-Z introductory markers (`A` Attention Getter, `B` But/Challenge, `C` Cure, `D` Development, `E` Experiments, `F` Findings) within a concise IEEE single-paragraph summary.

#### Scenario: Six-part abstract coverage
- **WHEN** the Abstract text is audited against `ref/A2Z_academic_writing_style.md`
- **THEN** it SHALL state the food waste problem, standalone LLM challenge, Food Guardian solution, layered architecture, 30-case evaluation setup, and observed pass/latency results

### Requirement: Introduction Follows G-L Structure
The Introduction section MUST address markers `G` through `L` (`G` General background, `H` However challenges, `I` In literature, `J` Judgement, `K` Keypoint contributions, `L` List Organization).

#### Scenario: Introduction roadmap and contributions
- **WHEN** Section I (`Introduction`) is reviewed
- **THEN** it SHALL contrast existing paradigms, enumerate Food Guardian's technical contributions, and conclude with a section-by-section organization roadmap

### Requirement: Related Work Follows M-O Taxonomy and Summary Table
The Related Work section MUST implement markers `M` through `O`, balancing AI methodology and food-domain knowledge (`M`), highlighting the hybrid trend (`N`), and presenting an Article Summary Table and SWOT/capability comparison (`O`).

#### Scenario: Related work comparative table
- **WHEN** Section II (`Related Work`) is reviewed
- **THEN** it SHALL include an Article Summary Table (`Ref. / Year / Problem / AI Method / Domain Knowledge / Dataset / Findings / Limitation`), a capability/SWOT comparison, and the explicit research-gap logic chain

### Requirement: Proposed Design Follows PA-PM Technical Specifications
The Proposed Design section MUST cover markers `PA` through `PM`, including an 8-step numbered architecture graph (`PG`), component responsibility mapping (`PE`), SQLite schema formulation (`PF`), Agent Flowchart and line-numbered `Algorithm 1` (`PI`), worked example (`PJ`), and mathematical equations (`PM`).

#### Scenario: Numbered architecture, flowchart, and pseudocode presence
- **WHEN** Section III (`Proposed Design`) is reviewed
- **THEN** it SHALL contain a numbered system architecture figure (`(1)`--`(8)`), an agent decision flowchart, a line-numbered `Algorithm 1` block, and formal equations matching `Food-Guardian/src/`

### Requirement: Experiment Follows Q-V Evaluation Protocol
The Experiment section MUST address markers `Q` through `V`, defining metrics (`Q`), baseline comparisons (`R`), simulation setup (`S`), tuning parameters (`T`), recorded results (`U`), and validity boundaries (`V`) using only verified `Food-Guardian/evaluation/results/` data.

#### Scenario: Honest reporting of offline and live metrics
- **WHEN** Section IV (`Experiment`) is reviewed
- **THEN** it SHALL report 25/25 offline passes (`5 NOT_RUN`), 3/3 non-RAG live tool passes (`11.710 s` mean latency, `1` retry), and explicitly flag `MUL-02`/`MUL-04` and human reviews as pending

### Requirement: Conclusion Follows W-Z Synthesis
The Conclusion section MUST address markers `W` through `Z` (`W` What Proposed, `X` eXcel scope strengths, `Y` Yields/deliverables, `Z` Zen future work).

#### Scenario: Deliverables and future work boundaries
- **WHEN** Section V (`Conclusion`) is reviewed
- **THEN** it SHALL summarize Food Guardian's scope, cite reproducible repository deliverables, and outline future directions without claiming unproven waste-reduction percentages

