# Proposal: ICEIB 2027 Academic Paper in A-to-Z Style

## Why

To publish the Food Guardian project at the **7th IEEE International Conference on Electronic Communications, Internet of Things and Big Data (ICEIB 2027)** (`https://www.iceib.asia/`), the manuscript in `ICEIB paper/main.tex` needs a formal specification and structural alignment with two standards: (1) standard two-column IEEE conference proceedings formatting (`IEEEtran`, 4--8 pages, English), and (2) the **A-to-Z (A2Z) academic writing SOP** documented in `ref/A2Z_academic_writing_style.md` across the six required sections (`Abstract`, `Introduction`, `Related Work`, `Proposed Design`, `Experiment`, `Conclusion`, plus `References`).

## What Changes

- Store the 36-marker A-to-Z academic writing style specification in `ref/A2Z_academic_writing_style.md`.
- Configure `openspec/config.yaml` with ICEIB 2027 formatting, A-to-Z structural rules, and strict codebase grounding constraints.
- Define OpenSpec capability specifications (`paper-structure-a2z`, `iceib-ieee-formatting`) governing manuscript sections, A-to-Z marker coverage, technical diagrams/algorithms, and factual verification against `Food-Guardian/`.
- Refactor `ICEIB paper/main.tex` to follow the exact section layout (`Abstract`, `Introduction`, `Related Work`, `Proposed Design`, `Experiment`, `Conclusion`, `References`) and embed all 36 A-to-Z writing elements cleanly without fabricating unverified metrics.

## Capabilities

### New Capabilities
- `paper-structure-a2z`: Governs section organization (`Abstract`, `Introduction`, `Related Work`, `Proposed Design`, `Experiment`, `Conclusion`, `References`) and complete coverage of the 36 A-to-Z writing markers (`A--F`, `G--L`, `M--O`, `PA--PM`, `Q--V`, `W--Z`) grounded in `Food-Guardian`.
- `iceib-ieee-formatting`: Governs ICEIB 2027 IEEE conference LaTeX compliance (`IEEEtran`, 2-column layout, IEEE keywords, numbered equations/tables/figures/algorithms, IEEE bibliography, ASCII/pdflatex cleanliness).

### Modified Capabilities
<!-- No existing specs in openspec/specs/ yet -->

## Impact

- `ref/A2Z_academic_writing_style.md`: Created as the canonical A-to-Z style guide.
- `openspec/config.yaml`: Updated with project writing constraints.
- `openspec/changes/iceib-paper/*`: Holds proposal, delta specs, design mapping, and task checklist.
- `ICEIB paper/main.tex`: Updated to the A-to-Z structured ICEIB IEEE conference manuscript.
- `Food-Guardian/`: Read-only reference source; codebase remains unmodified.

