# High-Level Design Document — Overleaf Template

Reusable modular HLDD template for engineering projects.

## Start here

Read **`HOW_TO_USE.md`** before creating a project.

## Core project artifacts

Every HLDD should normally contain:

1. **System Block Diagram**
2. **Circuit Diagram**
3. **Pseudocode / Algorithm** (for most projects)

The two diagrams belong in `figures/`:

```text
figures/
├── block_diagram.png
└── circuit_diagram.png
```

## Structure

- `main.tex` — document entry point
- `config.tex` — global styling and project metadata
- `project_exp.txt` — plain language project brief used as background when
  writing project-specific metadata and sections
- `HOW_TO_USE.md` — detailed usage guide
- `sections/` — modular document sections
- `figures/` — draw.io source files and exported diagram images
- `tables/` — optional external table assets

The template is based on the supplied HLDD document's visual structure and has
been made reusable by replacing project-specific content with placeholders.
