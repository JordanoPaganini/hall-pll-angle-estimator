# Hall PLL Angle Estimator

## Project Overview

`hall-pll-angle-estimator` is a standalone embedded project for reading three Hall sensor signals and estimating rotor angle with a phase-locked loop (PLL). It targets the STM32F407VET6 and runs bare-metal, without an RTOS.

The project may later provide angular information to a field-oriented control (FOC) system, but it is not currently an FOC project or a module of a larger formal ecosystem.

## Objective

Develop a reliable and efficient implementation that:

- reads the three digital Hall sensor signals;
- interprets valid Hall states and transitions;
- determines rotation direction;
- estimates speed;
- estimates mechanical and electrical rotor angle;
- uses a PLL as part of the final angle-estimation solution;
- exposes results suitable for future use by a motor-control application.

Intermediate implementations may use discrete sector estimation or angular interpolation, but they must support progress toward the required PLL-based estimator.

## Target Hardware and Runtime

- MCU: STM32F407VET6
- Inputs: three digital Hall sensor signals
- Runtime: bare-metal
- RTOS: none
- Primary implementation language: C

## Golden Rules

1. Keep the implementation efficient, clean, deterministic, and appropriate for an embedded bare-metal target.
2. Keep the project focused on Hall acquisition and PLL-based angle estimation. Do not silently expand it into a complete FOC implementation.
3. Avoid unnecessary abstractions, premature generalization, and excessive file fragmentation.
4. Do not create one documentation file per `.c` or `.h` file by default. Organize code documentation dynamically according to the actual complexity and conceptual boundaries of the project.
5. Write comments that explain non-obvious intent, constraints, or reasoning. Do not restate self-explanatory code or add redundant comments.
6. Keep GitHub code documentation and Notion engineering documentation separate. Follow [`.codex/documentation-standard.md`](.codex/documentation-standard.md).
7. Follow the versioning, changelog, branch, and commit rules in [`.codex/versioning-standard.md`](.codex/versioning-standard.md).
8. If a necessary engineering decision is not documented, do not invent it silently. Identify the gap explicitly and request or record a decision before relying on it.
9. Review all changed code and documentation before considering a task complete.

## Workflow

1. Confirm that the requested work is within the project's Hall-reading and PLL angle-estimation scope.
2. Inspect the relevant implementation and existing documentation before making changes.
3. Check whether the required engineering rationale or decision is documented in Notion. If it is missing and the choice is material, signal the documentation gap instead of silently choosing an assumption.
4. Implement the smallest coherent change that satisfies the requirement while preserving embedded efficiency and clarity.
5. Update GitHub code documentation in `docs/` when the code structure or behavior needs explanation.
6. Update or flag the need to update Notion when engineering logic, formulas, assumptions, algorithm behavior, or design decisions change.
7. Apply the repository's versioning and changelog rules when the change affects a release.
8. Review the complete diff for correctness, scope, consistency, unnecessary abstractions, excessive fragmentation, and redundant comments.
9. Run the relevant build, static checks, and tests when available. Report any check that could not be run.
10. Consider the task complete only after the implementation and its required documentation are consistent.

## Repository Language Rules

- Structural repository files and files under `.codex/` are written in English.
- Code documentation under `docs/` is written in Portuguese.
- Engineering documentation in Notion is written in Portuguese.
- Source-code identifiers follow the project's established conventions and should remain clear and consistent.

## References

- [Documentation standard](.codex/documentation-standard.md)
- [Versioning standard](.codex/versioning-standard.md)
