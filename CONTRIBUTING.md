# 📖 Contributing to Alis AI

## Overview
This document outlines the best practices for contributing to Alis AI’s instruction set.  
It ensures all updates follow a structured Git workflow, maintaining version control and consistency.

---

## Git Workflow

This project uses a structured Git workflow optimized for clarity, instruction versioning, changelog automation, and component-level traceability.

---

### Branching Strategy

All work must be done on topic branches and merged into `develop`.

| Branch             | Purpose                                      |
|--------------------|----------------------------------------------|
| `main`             | Stable, production-ready releases            |
| `develop`          | Integration branch for active changes        |
| `release/alis-vx.x`| Release staging, review, and version bumping |
| `comp/<component>` | Component-scoped work                        |

> 🔍 Use the `comp/` prefix to indicate branches tied to specific components or instruction systems.  
> Example branches:
> - `comp/developer-mode`
> - `comp/export-diff-preview`
> - `comp/validation-error-reporting`
---

### Commit Message Guidelines

Alis expects commit messages to follow a clear, readable structure optimized for user-facing changelogs and traceable version history.

#### Format

Each commit should follow this structure:

```
<Type>: <Short, imperative summary>

<Optional detailed description explaining what changed and why>
```

> ⚠️ **The colon (`:`) after the prefix is required.**  
> Commit messages that omit it will not be considered valid.

---

#### Prefixes

Allowed prefixes are all **imperative-phrased** and directly mapped to changelog categories.

| Prefix         | Mapped Category       | Purpose                                             |
|----------------|------------------------|-----------------------------------------------------|
| `Add:`         | 🆕 Features             | Introduce new behaviors, components, or logic       |
| `Implement:`   | 🆕 Features             | Implement full systems or capabilities              |
| `Integrate:`   | 🆕 Features             | Integrate new subsystems or external functionality  |
| `Fix:`         | 🐛 Fixes                | Resolve bugs, unintended behavior                   |
| `Resolve:`     | 🐛 Fixes                | Same as `Fix:`, alternate phrasing                  |
| `Refactor:`    | 🔁 Refactoring          | Reorganize code/structure without behavior change   |
| `Rename:`      | 🔁 Refactoring          | Rename files, functions, sections                   |
| `Remove:`      | 🔁 Refactoring          | Remove unused or redundant parts                    |
| `Drop:`        | 🔁 Refactoring          | Forcefully remove deprecated logic or features      |
| `Rewrite:`     | 🔁 Refactoring          | Rewrite logic or structure                          |
| `Reword:`      | 🔁 Refactoring          | Adjust textual content or phrasing without behavior change |
| `Write:`       | 📚 Documentation        | Create or significantly expand documentation        |
| `Clarify:`     | 📚 Documentation        | Refine or correct documentation wording             |
| `Test:`        | ✅ Tests                | Add or improve tests                                |
| `Optimize:`    | 🚀 Optimization         | Enhance performance, efficiency, or clarity         |
| `Improve:`     | 🚀 Optimization         | General improvements in logic or flow               |

> 🔐 All prefixes **must include a colon (`:`)**.  
> Example: `Implement: instruction export flow logic`

Alis uses this prefix mapping to classify changelog entries during generation.

---

**Guidelines for Prefix Usage:**

- ✅ All prefixes must be used with a colon (e.g., `Fix:`, not `Fix`)
- ✅ Choose the prefix that best matches the **type of change**, not just the file touched
- ✅ All prefixes must be **imperative verbs**
- ✅ Commit summaries should describe **what changed**, not why — use the body for rationale
- ✅ If a negating verb is used (`skip`, `remove`, `disable`), be sure to clarify what was added, changed, or replaced

---

#### Writing Commit Messages

- ✅ Use **imperative mood** in the summary  
  (e.g., `Add: validate-instructions dry-run mode`, not `Added` or `Adding`)
- ✅ Keep the **summary line as short as possible without losing necessary context**
  - Recommended: under 50 characters
  - Maximum: 72 characters
- ✅ Use the body (description) to elaborate on conditions, motivations, or technical implications if needed
- ✅ Each commit message should describe **one change**, clearly
- ✅ **Do not reuse** the same message for multiple commits, even if similar
- ✅ Describe **what** was done in the subject, and **why** in the body (if applicable)

---

#### Linking Issues or Related Work

Use [GitHub-compatible references](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/autolinked-references-and-urls#issues-and-pull-requests) in commit bodies when referencing related issues, features, or discussions.

```
Fix: incorrect instruction file validation order

Fixes #42 — behavior mismatch during export generation.
```

---

#### Fix Commits

- `Fix:` commits must **always reference a GitHub issue** (e.g., `Fixes #123`)
- The issue should describe the full problem and context
- The commit should contain a **brief summary** of the resolution only

---

#### Avoid

- Vague summaries like `Fix things`, `Update`, or `Misc edits`
- Mixing unrelated changes into a single commit
- Passive/log-style prefixes (`Rename`, `Resolve`) without a colon
- Omitting the prefix colon (e.g., `Fix something` instead of `Fix: something`)

---

#### Rewriting Commit History

You may **squash, amend, or rewrite** commits during a feature's development.  
However, if you change any commit messages **after a changelog was generated**,  
you must **regenerate the entire changelog** for the affected release.

Why?

- Alis links changelog entries to Git history and expects them to match
- Outdated messages or missing links may invalidate changelog grouping or summaries

---

#### Examples

```
Fix: correct diff marker formatting in preview table

Fixes #87 — incorrect '+' symbol applied to changed lines.
```

```
Add: structured output changelog support
```

```
Docs: clarify reinforcement rule formatting behavior
```

---

### Release Workflow

1. Create your branch from `develop` using a component-focused slug
2. Make and commit changes following message format
3. Push your branch
4. Merge into `develop`
5. When preparing a release, create a `release/alis-vx.x` branch
6. Open a PR from the release branch to `main`

> 🔐 PRs are only required for release branches


#### Workflow Diagram

```
[ develop ]
     ↓
[ feature/component branch ]
     ↓
    (merge)
     ↓
[ develop ] ←←←←←←←←←←←←←←←←←←←←←←←←←←←←←
     ↓                                 ↑
     ↓                             Commit, Merge,
[ release/alis-vx.x ] ←←←←←←←←←←←←←←←←  Validate
     ↓
     ↓ PR → Validate Instructions
     ↓      Generate Changelog
     ↓
[  main  ] ←←←←←←←←←←←←←←←←←←←←←←←←
-> Final Production Release
```

- 🧠 `develop`: Ongoing changes and staging for releases
- 🧩 `feature/component`: Localized feature or fix work
- 🚀 `release/alis-vx.x`: Polish, finalize, bump version, changelog generation
- ✅ `main`: Stable, final release-ready instruction state

---

### Changelog Automation

Alis automatically generates changelog entries based on commit messages and changed file paths (via a metadata map).

- **Category** → Inferred from the commit prefix (`Add:`, `Fix:`, etc.)
- **Component** → Determined by which files were affected, using the component metadata file

> Example:
>
> ```
> Commit: Add: export skip and abort step logic
> Files: src/developer-mode.md
> ```
> 
> Will generate:
>
> ### 🆕 Features  
> #### 🧩 developer-mode  
> - Add: export skip and abort step logic

---

### Release Process

- All release PRs must be made from a `release/alis-vx.x` branch to `main`
- All commits merged into `main` **must** be validated first via:
  - ✅ `validate-instructions` (Alis will enforce structure and consistency)
  - ⚙️ Optionally: Run a changelog dry-run to preview generated output

---

🛡️ Alis uses changelog entries as part of its behavioral record. Clean, descriptive commits and consistent prefix usage ensure accurate version history.
