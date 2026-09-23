# HOW TO USE — HLDD Overleaf Template

## 1. Purpose

This is a reusable High-Level Design Document (HLDD) template for engineering
projects. The template separates the visual/document standard from the
project-specific technical content.

Every project should normally contain:

- A system block diagram
- A circuit diagram
- A pseudocode / algorithm section
- Hardware and software descriptions
- Constraints and engineering objectives
- Bill of Materials (BOM)
- Project execution plan
- Risk assessment
- Academic / engineering alignment
- References

---

## 2. Create a New Project

Do not edit the master template directly.

### In Overleaf

1. Create a new blank Overleaf project.
2. Upload the contents of this template folder.
3. Keep the same folder structure.
4. Open `main.tex`.
5. Compile once before making changes.
6. Then customize `config.tex` and the section files.

---

## 3. Folder Structure

```text
overleaf_hldd_template/
│
├── main.tex
├── config.tex
├── HOW_TO_USE.md
├── README.md
│
├── sections/
│   ├── titlepage.tex
│   ├── document_control.tex
│   ├── introduction.tex
│   ├── problem_statement.tex
│   ├── objectives.tex
│   ├── methodology.tex
│   ├── firmware.tex
│   ├── bom.tex
│   ├── execution_plan.tex
│   └── conclusion.tex
│
├── figures/
│   ├── block_diagram.png
│   ├── circuit_diagram.png
│   └── README.txt
│
└── tables/
```

---

# 4. First File to Edit — `config.tex`

The document's global metadata and visual configuration are in:

```text
config.tex
```

At the beginning of a project, update:

```latex
\newcommand{\DocumentTitle}{PROJECT TITLE}
\newcommand{\DocumentSubtitle}{Core Specifications \& System Blueprint}
\newcommand{\DocumentType}{HIGH LEVEL DESIGN DOCUMENT}
\newcommand{\DocumentID}{PROJECT-HLDD-2026-001}
\newcommand{\DocumentVersion}{1.0.0}
\newcommand{\ReleaseDate}{Month DD, YYYY}
\newcommand{\PreparedFor}{Final Year B.Tech Academic Project}
\newcommand{\CompiledBy}{Organization / Team Name}
\newcommand{\TargetFramework}{University / Academic Framework}
\newcommand{\HeaderTitle}{PROJECT / SYSTEM NAME}
\newcommand{\HeaderVersion}{HLDD V1.0}
\newcommand{\FooterText}{Confidential - Internal Architecture Framework}
```

These values automatically appear on the title page, header, footer, and PDF
metadata where applicable.

### Do not normally modify

The following sections of `config.tex` define the common visual standard:

- Package imports
- Color palette
- Header/footer formatting
- Section heading styles
- Code listing styles
- TikZ styles
- Hyperlink styling

Only change these if the organization wants to change the master document style.

---

# 5. Add the Two Standard Figures

Every HLDD should have two main technical figures.

## Figure 1 — System Block Diagram

Place the file here:

```text
figures/block_diagram.png
```

It is automatically inserted by:

```latex
\includegraphics[
    width=0.92\textwidth,
    height=0.58\textheight,
    keepaspectratio
]{figures/block_diagram}
```

### What the block diagram should show

Show the functional architecture:

```text
Input
  ↓
Controller / Processing
  ↓
Actuator / Output

with sensors, communication, power, UI, cloud/server,
or other major functional blocks as applicable.
```

Do not use the block diagram for detailed component-level wiring.

---

## Figure 2 — Circuit Diagram

Place the file here:

```text
figures/circuit_diagram.png
```

It is automatically inserted by:

```latex
\includegraphics[
    width=0.95\textwidth,
    height=0.62\textheight,
    keepaspectratio
]{figures/circuit_diagram}
```

### What the circuit diagram should show

Show the electrical implementation:

- Controllers
- Sensors
- Actuators
- Power supply
- Regulators
- Drivers
- Protection
- Connectors
- Communication interfaces
- Important component values

Make sure the diagram remains readable when printed.

---

# 6. Recommended Figure Format

For engineering diagrams, prefer:

```text
PDF > PNG > JPG
```

PDF is preferred for vector diagrams.

If using PNG:

- Use high resolution.
- Avoid screenshots where possible.
- Make labels readable.
- Avoid excessive whitespace.

If you use a different filename, update the corresponding
`\includegraphics{...}` command in:

```text
sections/methodology.tex
```

---

# 7. Pseudocode

Most projects should include pseudocode.

The standard location is:

```text
sections/methodology.tex
```

The template already includes an `algorithm2e` pseudocode environment.

Example:

```latex
\begin{algorithm}[H]
\caption{System Operating Algorithm}

Initialize system\;
Initialize sensors\;

\While{system is active}{
    Read sensor data\;
    Process data\;

    \eIf{condition is normal}{
        Generate output\;
    }{
        Trigger fault response\;
    }
}

Shutdown system safely\;

\end{algorithm}
```

### What pseudocode should describe

Pseudocode should describe the **system logic**, not reproduce the actual
programming language source code.

For example:

```text
Initialize
↓
Read sensor
↓
Validate data
↓
Process
↓
Decision
↓
Control actuator
↓
Update display
↓
Repeat
```

Use actual source code only when implementation details are specifically
required. The firmware section can contain representative code separately.

---

# 8. Section-by-Section Editing

## `sections/titlepage.tex`

Normally no editing is required.

It automatically uses metadata from `config.tex`.

---

## `sections/document_control.tex`

Fill in:

- Revision history
- Document purpose
- Target audience
- Executive abstract
- Academic / organizational alignment

---

## `sections/introduction.tex`

Describe:

1. Existing system / industry context
2. Current limitations
3. Integration challenge
4. Proposed solution concept
5. High-level architecture

---

## `sections/problem_statement.tex`

Define:

- Formal problem statement
- Engineering constraints
- Physical constraints
- Electrical constraints
- Computational constraints
- Cost constraints
- Environmental constraints
- Regulatory/interface constraints
- Operational targets

Do not add arbitrary constraints. Use values that have been established for
the actual project.

---

## `sections/objectives.tex`

Define the engineering objectives.

Objectives should be measurable where possible.

Example:

```text
Design a system capable of measuring X within Y accuracy.
```

is preferable to:

```text
Design a highly accurate system.
```

---

## `sections/methodology.tex`

This is the main technical section.

The standard order is:

```text
5.1 System Architecture
    → Block Diagram

5.2 Hardware / Circuit Design
    → Circuit Diagram

5.3 Subsystem Configuration
    → Individual subsystem descriptions

5.4 Software / Control Logic
    → Software architecture

5.5 Pseudocode / Algorithm
    → Main system algorithm

5.6 Operating Sequence
    → Normal operation
```

The two main diagrams should not be removed unless the project genuinely does
not contain the corresponding engineering artifact.

---

## `sections/firmware.tex`

Use this for:

- Firmware architecture
- Communication protocols
- Data structures
- Processing logic
- Algorithms
- Fault detection
- Alert handling
- Representative source code

Do not duplicate the complete source code of the project unless required.

---

## `sections/bom.tex`

Add the complete prototype BOM.

Recommended columns:

```text
Item
Component Name
Specification
Quantity
Unit Cost
Total Cost
```

Update the cumulative budget.

---

## `sections/execution_plan.tex`

Define:

- Development phases
- Milestones
- Timeline
- Critical path
- Risks
- Mitigation

Update the example Gantt chart to match the actual project.

---

## `sections/conclusion.tex`

Include:

- Academic / framework alignment
- Engineering outcomes
- Ethical and safety considerations
- Final design summary
- Future development

---

# 9. Adding References

References are maintained at the end of:

```text
main.tex
```

Example:

```latex
\begin{thebibliography}{99}

\bibitem{reference1}
Author,
\emph{Title},
Publisher/Journal, Year.

\end{thebibliography}
```

Cite them in the document using:

```latex
\cite{reference1}
```

For a larger project, this template can later be converted to a `.bib` /
BibTeX-based reference system.

---

# 10. Recommended Workflow

Use this order when preparing a new HLDD:

```text
1. Define project
       ↓
2. Update config.tex
       ↓
3. Prepare block diagram
       ↓
4. Prepare circuit diagram
       ↓
5. Write problem statement
       ↓
6. Define objectives
       ↓
7. Describe architecture
       ↓
8. Describe hardware
       ↓
9. Describe software/control logic
       ↓
10. Write pseudocode
       ↓
11. Prepare BOM
       ↓
12. Prepare execution plan
       ↓
13. Add risks and mitigation
       ↓
14. Add references
       ↓
15. Compile and check PDF
       ↓
16. Final technical review
```

---

# 11. Final Review Checklist

Before submitting an HLDD, verify:

### Document
- [ ] Project title is correct
- [ ] Document ID is correct
- [ ] Version is correct
- [ ] Date is correct
- [ ] Author / organization is correct
- [ ] Header/footer is correct

### Technical
- [ ] Block diagram included
- [ ] Circuit diagram included
- [ ] Subsystems described
- [ ] Inputs and outputs identified
- [ ] Interfaces identified
- [ ] Pseudocode included
- [ ] Operating sequence explained
- [ ] Failure handling addressed

### Engineering
- [ ] Constraints have measurable values where applicable
- [ ] BOM is complete
- [ ] Costs are calculated
- [ ] Timeline is realistic
- [ ] Risks and mitigations are documented

### Presentation
- [ ] Figures are readable
- [ ] Tables fit the page
- [ ] No placeholder text remains
- [ ] Captions are present
- [ ] Figure references are correct
- [ ] No blank pages
- [ ] No compilation warnings affecting the document

---

# 12. Master Template Principle

The template should remain visually consistent across projects.

Project-specific changes should normally be limited to:

```text
config.tex
sections/*.tex
figures/*
tables/*
references
```

Do not change the global visual style for individual projects unless there is
a specific requirement.

This ensures that all HLDD documents produced by the organization have a
consistent professional appearance.

## 13. If the diagrams are not ready yet

The template is designed to compile even when the two project diagrams have
not been added yet. `methodology.tex` automatically displays a placeholder
box until one of the following files exists:

```text
figures/block_diagram.pdf
figures/block_diagram.png
figures/block_diagram.jpg

figures/circuit_diagram.pdf
figures/circuit_diagram.png
figures/circuit_diagram.jpg
```

This means you can start writing the document before the diagrams are finalized.
