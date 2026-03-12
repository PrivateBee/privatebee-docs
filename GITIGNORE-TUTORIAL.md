# .gitignore Tutorial

## Purpose

The `.gitignore` file tells Git which files and folders should **not** be tracked in the repository.

Use it to keep the repository clean, avoid committing local-only files, and prevent accidental sharing of sensitive data.

---

## What to put in `.gitignore`

Add files that are:

- generated automatically (build outputs, caches, logs),
- specific to your local environment (IDE settings, OS files),
- temporary or disposable,
- sensitive (for example `.env` files with secrets).

---

## Good practices

- Keep rules **simple and readable**.
- Prefer **project-level rules** useful for all contributors.
- Add comments to explain non-obvious rules.
- Review rules regularly to remove outdated entries.

---

## What to avoid

- Do not ignore source files that should be versioned.
- Do not rely on `.gitignore` alone to protect secrets already committed.

If a secret was committed, rotate it and remove it from Git history.

---

## Example

```gitignore
# Local environment variables
.env
.env.*

# Dependency folders
node_modules/

# Build outputs
dist/
build/

# Logs
*.log
```

---

## Summary

Use `.gitignore` to exclude local, generated, temporary, and sensitive files from version control, while keeping all important project files tracked.
