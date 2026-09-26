# Instructions for AI Agents

## Purpose

Maintain this reusable High-Level Design Document (HLDD) template. Keep the
shared structure and visual style reusable across projects, and use project
specific details only when the project owner supplies them or they are
supported by sources in the workspace.

## Project information and source of truth

- `project_exp.txt` is the owner's informal project brief when present. Use it
  as context for drafting metadata and section content. It is not included in
  the compiled PDF unless the owner asks for that behavior.
- Treat supplied project files, measurements, drawings, and user statements as
  project evidence. Distinguish confirmed facts from assumptions, estimates,
  alternatives, and open questions.
- Do not invent project names, requirements, component selections, ratings,
  calculations, prices, test results, affiliations, dates, or approvals. Keep
  unknown values explicitly TBD or ask when they block the requested work.
- If project notes, diagrams, source files, and document text disagree, report
  the mismatch and avoid silently choosing a version as fact.
- The template does not identify a permanent example project. Remove residual
  project-specific content when converting or improving the master template;
  use neutral prompts or clearly marked examples instead.

## Template structure and configuration

- `main.tex` is the document entry point. It loads `config.tex`, then the title
  page and modular files in `sections/`, followed by the bibliography.
- Keep project metadata and shared page styling centralized in `config.tex`.
  Do not duplicate global color, heading, typography, or page-style settings in
  section files.
- Keep sections modular. Preserve the current structure unless the user asks
  for a structural change; update cross-references when headings, labels, or
  section order change.
- Replace generic prompts with project-specific prose only when the owner has
  supplied enough information. Do not leave contradictory template examples in
  the final project document.
- The master template should remain project-neutral. Do not put a specific
  project's title, parts, calculations, or design decisions into shared
  instructions unless clearly labeled as an optional example.

## Figures and diagrams

- Store diagram source files, including `.drawio` files, in `figures/`.
- LaTeX displays exported image assets, not `.drawio` source files. Use the
  supported formats and filenames documented in `figures/README.txt` and
  `HOW_TO_USE.md`; update those instructions if support changes.
- Keep the editable source and exported image consistent whenever either is
  changed. Do not modify a source diagram without updating its export when the
  user expects the rendered document to reflect the change.
- Only include supplied or approved project figures from `figures/`. Do not
  create extra diagrams with TikZ, ASCII art, or other generated drawing code
  unless the user asks for them.
- Do not invent diagram contents. Flag missing, unclear, or inconsistent
  information for the owner.

## Technical writing and references

- Write concise, specific engineering prose. Use SI units and show equations,
  substitutions, units, assumptions, and interpretation when calculations are
  relevant.
- Label preliminary estimates and assumptions. Do not present an estimate as a
  verified rating, capacity, performance result, or safety limit.
- Use readable tables with wrapped columns. Mark unknown costs or quantities
  TBD rather than inventing them.
- Use LaTeX labels for figures, tables, and sections that are cross-referenced;
  keep references and captions synchronized with the content.
- Do not add unsupported technical, safety, regulatory, clinical, or
  performance claims. When accuracy depends on external technical information,
  check an authoritative source and cite it appropriately.
- Never invent bibliographic details. Verify citations against the cited paper,
  publisher, standard, or other authoritative source before adding them.

## Repository workflow

- Treat the checked-out repository and current branch as authoritative. Do not
  assume a repository name, remote, branch, or tracking relationship from a
  previous project.
- Do not commit or push unless the user asks. Never force-push or overwrite
  remote history to resolve a rejected push. Fetch and inspect remote changes,
  then rebase or merge when appropriate.
- Avoid committing generated or machine-specific files such as `.DS_Store`
  unless the user explicitly requests them.
- Report material changes, verification performed, and any unresolved issues
  accurately. Do not claim that the document compiled unless it was compiled.
