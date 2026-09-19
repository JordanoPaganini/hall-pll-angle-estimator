# Versioning Standard

## Version Scheme

Use Semantic Versioning in the form `MAJOR.MINOR.PATCH`, with Git release tags prefixed by `v`.

The project starts at:

```text
v1.0.0
```

Increment versions as follows:

- `MAJOR`: incompatible changes to established behavior or interfaces.
- `MINOR`: backward-compatible functionality or a meaningful new capability.
- `PATCH`: backward-compatible fixes or small corrections.

Do not change the version solely because documentation or internal organization changed unless that change is part of a release that warrants a new version.

## Changelog

Maintain a concise `CHANGELOG.md` focused on changes that matter to users or maintainers.

- A changelog entry is required for every `MAJOR` release.
- A changelog entry is required for every `MINOR` release.
- Add a changelog entry for a `PATCH` release when the fix or correction is relevant enough to communicate.
- Omit routine internal details, noisy commit-by-commit summaries, and changes with no practical release impact.

Group entries by version and keep descriptions short, concrete, and consistent with the released code.

## Branching Model

Develop directly on `main`.

Do not create feature, fix, release, documentation, experiment, or other routine development branches.

Branches named `legacy/vN` are reserved exclusively for preserving legacy major-version lines, where `N` is the preserved major version, for example:

```text
legacy/v1
```

Do not use `legacy/vN` branches for active feature development, experiments, release preparation, or ordinary maintenance of `main`.

## Commit Messages

Use Conventional Commits. Every activity in a commit message must have its own line in this format:

```text
<type>(<scope>): <description>
```

Place `[Codex]` immediately after the colon only on lines describing work performed by Codex. Do not tag work performed by the user, even when Codex creates the commit. The first activity line is the commit subject. For commits containing multiple activities, follow it with one formatted line per additional activity. Do not add unformatted narrative paragraphs or attribution notes.

Single-activity examples:

```text
feat(pll): [Codex] add rotor angle tracking loop
fix(hall): reject invalid transition sequence
```

Mixed-activity example:

```text
chore(stm32): add user-configured CubeMX project
chore(git): [Codex] add STM32 ignore rules
```

Use an established Conventional Commits type such as `feat`, `fix`, `docs`, `refactor`, `test`, `build`, `ci`, `chore`, `perf`, or `revert`. Keep the description concise, imperative, and specific.

For a breaking change, add `!` before the colon on the affected activity line and explain the impact in its description.

## Release Review

Before assigning a version or creating a release tag:

1. review the complete set of release changes;
2. verify that the selected SemVer increment matches their impact;
3. confirm that all required changelog entries are present and concise;
4. verify that code and documentation are consistent;
5. confirm that relevant checks have passed or that any unavailable checks are reported;
6. create the `vMAJOR.MINOR.PATCH` tag only from the intended reviewed state of `main`.
