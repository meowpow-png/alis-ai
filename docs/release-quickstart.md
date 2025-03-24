# 🚀 Release Quickstart

Use this guide when you're ready to finalize and publish a new version of Alis.

---

## 1. Prep Your Release Branch

Start from the latest `develop` branch:

```bash
git checkout develop
git pull
git checkout -b release/alis-vX.Y
```

---

## 2. Finalize, Polish, and Validate

- [ ] Complete all feature and fix work
- [ ] Ensure all instruction files are updated and tested
- [ ] Run validation:

```bash
validate-instructions
```

---

## 3. Generate Changelog

Use Alis to build the changelog for the release:

```bash
changelog generate --version vX.Y
```

Confirm the entry was prepended to `CHANGELOG.md`.  
Alis will also provide a separate file for the version (e.g., `alis-v1.3-changelog.md`).

---

## 4. Create a Pull Request

Push the release branch:

```bash
git push -u origin release/alis-vX.Y
```

Open a pull request from the release branch to `main`.

---

## 5. PR Format

### Title:
```
Release: <fun, themed name>
```

### Description:
```
- Version: vX.Y
- Summary: <brief description of the release scope>
- Includes: <component slugs>
- Linked Issues: #<id>, ...
```

---

## 6. Final Review and Merge

- [ ] Pass instruction validation
- [ ] Commit generated changelog
- [ ] Confirm final `Release:` commit message
- [ ] Merge PR into `main`

🎉 Alis vX.Y is now live!
