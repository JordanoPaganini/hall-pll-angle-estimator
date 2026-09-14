# Documentation Standard

## Purpose

This standard defines where project knowledge belongs and how it should be maintained. The goal is to keep code documentation practical and engineering documentation rigorous without duplicating the same material across GitHub and Notion.

## Language

- GitHub code documentation under `docs/` must be written in Portuguese.
- Notion engineering documentation must be written in Portuguese.
- Structural repository files and files under `.codex/`, including this standard, must be written in English.

## GitHub: Code Documentation

GitHub documentation explains the implementation as it exists in the repository. It should help a reader understand the code without reproducing every line or turning documentation into a fixed checklist.

Document, when useful:

- the responsibility of relevant functions or groups of functions;
- how important source components interact;
- data flow through Hall acquisition, state interpretation, estimation, and outputs;
- code-level behavior that is not immediately evident from the implementation;
- organization or execution details needed to understand or maintain the code.

Keep this documentation simple, necessary, objective, and organized. Do not require sections such as public interface, limitations, precautions, or usage examples unless the actual code warrants them.

### Organization of `docs/`

Store code documentation in `docs/` and organize it dynamically according to the project's current needs.

- Do not force all documentation into a single file.
- Do not create a dedicated document for every `.c` or `.h` file by default.
- Split a document when distinct concepts become difficult to navigate together.
- Merge or avoid documents when separation would create small, repetitive, or low-value files.
- Choose filenames and structure based on stable code concepts, not an arbitrary template.

For example, Hall reading, angle estimation, and the PLL may eventually justify separate documents, but only when their implementation complexity makes that separation useful.

## Notion: Engineering Documentation

Notion is the source for the engineering rationale behind the project. Its content must be objective, standardized, well organized, and specific to `hall-pll-angle-estimator`.

Document, as applicable:

- the engineering logic of Hall sensor reading and transition interpretation;
- valid Hall states, sequence assumptions, and direction determination;
- the reasoning, equations, inputs, outputs, and behavior of the PLL;
- mechanical- and electrical-angle estimation;
- speed-estimation methods;
- assumptions, trade-offs, and design decisions;
- validation criteria and engineering conclusions.

When an algorithm such as the PLL is implemented or materially changed, Notion must explain what it does, how it works, and the engineering reasoning behind it. GitHub may contain a simple reference to the corresponding Notion material instead of duplicating that explanation.

## Separation of Responsibilities

Use the following boundary:

- Notion answers: **Why was this engineering approach chosen, and how does the underlying method work?**
- GitHub `docs/` answers: **How is the current code organized, what do its relevant functions do, and how do they interact?**

Small overlaps are acceptable when they provide necessary context, but avoid maintaining duplicate explanations that can diverge.

## Missing Engineering Decisions

If implementation work requires an engineering decision that is not documented, do not introduce the decision as an unstated assumption.

Instead:

1. identify the missing decision clearly;
2. state why it affects the implementation;
3. request clarification or explicitly record the agreed decision in Notion;
4. proceed only with assumptions that have been made visible and accepted when the decision is material.

## Documentation Quality Review

Before completing a task that changes documentation, verify that:

- the content is in the correct location and language;
- GitHub documentation describes code rather than replacing engineering rationale;
- Notion documentation captures new or changed engineering logic;
- the structure fits the current project rather than a rigid file template;
- the writing is concise, accurate, and free of unnecessary repetition;
- links and references remain valid;
- documentation agrees with the reviewed implementation.
