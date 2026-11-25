# Spec Delta

## Purpose

Defines the IEEE conference LaTeX formatting and ICEIB 2027 submission compliance rules for `ICEIB paper/main.tex` to ensure clean compilation and proceedings readiness.

## ADDED Requirements

### Requirement: IEEEtran Conference Document Class
The manuscript MUST use `\documentclass[conference]{IEEEtran}` in English with a two-column conference layout, `\begin{abstract}...\end{abstract}`, and `\begin{IEEEkeywords}...\end{IEEEkeywords}`.

#### Scenario: IEEEtran preamble check
- **WHEN** `ICEIB paper/main.tex` preamble is inspected
- **THEN** it SHALL declare `\documentclass[conference]{IEEEtran}`, include standard IEEE packages (`cite`, `amsmath`, `algorithm`, `algorithmic`, `booktabs`, `tikz`), and define author metadata

### Requirement: pdflatex ASCII Cleanliness and Self-Contained Diagrams
The LaTeX source MUST remain pure ASCII so it compiles without Unicode inputenc errors under standard `pdflatex`, and all diagrams MUST render via standalone TikZ without missing external image dependencies.

#### Scenario: ASCII and standalone diagram verification
- **WHEN** `ICEIB paper/main.tex` is scanned for non-ASCII characters and external graphics
- **THEN** zero non-ASCII characters SHALL exist and all figures SHALL be constructed with valid TikZ environments

### Requirement: IEEE Numbered Citations and Caption Placement
All references MUST use consecutive IEEE numbered `\bibitem` entries (`\cite{...}`), with table captions placed above tables and figure captions placed below figures.

#### Scenario: Caption and citation consistency
- **WHEN** tables, figures, and bibliography entries in `ICEIB paper/main.tex` are checked
- **THEN** every `\cite{...}` key SHALL resolve to a `\bibitem` entry, table captions SHALL precede `tabular`, and figure captions SHALL follow `tikzpicture`

