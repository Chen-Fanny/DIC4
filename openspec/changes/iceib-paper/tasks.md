# Tasks

## 1. Style Reference and OpenSpec Setup

- [x] 1.1 Extract the 36-marker A-to-Z (A2Z) SOP from `Food-Guardian/系統設計提案解析.pdf` into `ref/A2Z_academic_writing_style.md` and verify `ref/` contains the file
- [x] 1.2 Initialize OpenSpec (`openspec init --tools antigravity`) and configure `openspec/config.yaml` with ICEIB 2027 and A-to-Z context rules
- [x] 1.3 Create `proposal.md`, `specs/paper-structure-a2z/spec.md`, `specs/iceib-ieee-formatting/spec.md`, `design.md`, and `tasks.md`, and verify with `openspec validate iceib-paper --strict`

## 2. Manuscript Refactoring in A-to-Z ICEIB IEEE Style

- [x] 2.1 Preserve author block (`Yi-Fan Chen`, NCHU) and rewrite `Abstract` (`A--F`) and `I. Introduction` (`G--L`) in `ICEIB paper/main.tex`
- [x] 2.2 Write `II. Related Work` (`M--O`) with balanced AI + Domain subsections, Article Summary Table (`Table I`), SWOT/Capability Matrix (`Table II`), and research-gap chain
- [x] 2.3 Write `III. Proposed Design` (`PA--PM`) with numbered `(1)--(8)` TikZ architecture diagram (`Fig. 1`), Module Matrix (`Table III`), SQLite Schema (`Table IV`), Agent Flowchart (`Fig. 2`), line-numbered `Algorithm 1`, math formulations, and worked example (`PJ`)
- [x] 2.4 Write `IV. Experiment` (`Q--V`) with metrics, Baseline 1/2 comparison, setup/tuning parameters, and recorded v3.3 offline (`Table V`) and live (`Table VI`) results
- [x] 2.5 Write `V. Conclusion` (`W--Z`) and verify `References` (`\bibitem` alignment)

## 3. Final Validation

- [x] 3.1 Run `openspec validate iceib-paper --strict` and verify `ICEIB paper/main.tex` is pure ASCII with matching `\cite`/`\ref`/`\label` pairs and zero fabricated numbers

## Workflow follow-up

- Compile `ICEIB paper/main.tex` in Overleaf or local `pdflatex` to confirm page count falls within ICEIB 2027's 4--8 page limit.
- Archive the `iceib-paper` OpenSpec change after final author review (`openspec archive iceib-paper`).
