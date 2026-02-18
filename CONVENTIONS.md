# Conventions

This document describes the coding and workflow conventions to follow when contributing to the Private Bee project.

---

## Table of Contents

- [General Naming Conventions](#general-naming-conventions)
- [File and Directory Naming Conventions and Structure](#file-and-directory-naming-conventions-and-structure)
    - [Naming Conventions](#naming-conventions)
        - [File](#file)
        - [Directory](#directory)
    - [Project Structure](#project-structure)
- [Branch Naming Conventions](#branch-naming-conventions)
    - [Basic Rules](#basic-rules)
    - [Branch Prefixes](#branch-prefixes)
    - [Issue-Specific Branches](#issue-specific-branches)
    - [Branch Name Examples](#branch-name-examples)
- [Commit Message Conventions](#commit-message-conventions)
    - [Basic Rules](#basic-rules-1)
    - [Commit Message Prefixes](#commit-message-prefixes)
    - [Scope](#scope)
    - [Important Changes](#important-changes)
    - [Commit Message Examples](#commit-message-examples)
- [Issue Conventions](#issue-conventions)
    - [Issue Templates](#issue-templates)
    - [How to Create an Issue](#how-to-create-an-issue)
    - [Issue Title Guidelines](#issue-title-guidelines)
    - [Filling Templates](#filling-templates)
- [Pull Request Conventions](#pull-request-conventions)
    - [Using the PR Template](#using-the-pr-template)
    - [Required Content](#required-content)
    - [Title Guidelines](#title-guidelines)
    - [Good Practices](#good-practices)

---

## General Naming Conventions

Naming conventions ensure your codebase remains **clear** and **maintainable**. Several naming conventions exist, such as:

- **camelCase:** `myFileName.c`
- **snake_case:** `my_file_name.c`
- **kebab-case:** `my-file-name.c`
- **PascalCase:** `MyFileName.c`

Please choose a naming convention for your project and apply it **consistently**. Your team can also use **different conventions** for **different contexts** (files, variables, functions, etc.) as long as each context is **consistent**.

---

## File and Directory Naming Conventions and Structure

File and directory structure conventions vary from one project to another. The Private Bee project uses files and software from a wide variety of sources, making it impractical to define a single universal structure. However, following **consistent** naming and organization **practices** will keep your project **clean** and **maintainable** over time.

As for the naming conventions, you can apply the following advice for your project, and adapt it if necessary.

---

### Naming Conventions

The most important aspect of naming conventions is **consistency**. Indeed, it is important to agree on a naming convention for files and directories with your team and apply it uniformly **throughout the project**.

#### File

Refer to the [General Naming Conventions](#general-naming-conventions) section for available naming styles. For files specifically, keep these guidelines in mind:

1. **Clear and descriptive names:** Indicate the file's purpose from its name
2. **Lowercase:** Use lowercase to prevent issues on case-sensitive filesystems
3. **Appropriate extensions:** Use correct file extensions (`.c`, `.h`, `.js`, etc.)

---

#### Directory

Using **standardized directories** can help improve the organization and maintainability of your project, as it allows developers from any horizon to easily locate and understand the purpose of different parts of the codebase based on the directory names.

Here is a list of the **common standardized directories** you can use for your project:

* **src:** Contains the source code for your project. It may include subdirectories for different parts of the codebase, depending on the part of the project you're working on.
* **build:** Contains the compiled version of your code, which is ready for deployment or distribution.
* **resources OR assets:** Contains static assets or resources that are needed by your project, such as images, fonts, or other media.
* **test:** Contains the common tests and testing tools for your project. It may include unit tests, integration tests, and other types of tests and tooling that are used to validate the global behavior and functionality of your code.
* **scripts:** Contains utility scripts or build scripts that are used to automate tasks such as building your code.
* **config:** Contains configuration files or settings for your project. These configuration files can be written in various formats and can contain any type of data that is relevant to the project's configuration except sensitive information.
* **docs:** Contains documentation for your project, such as user guides, technical specifications, etc. Its purpose is to provide detailed information about the project.

---

### Project Structure

Keeping your file structure **as flat as possible** is a good way to improve the organization and maintainability of your project. It reduces the need for **deep nesting** of directories and can make it easier to locate and access the files you need.

Of course, it is sometimes better to use a more deeply nested file structure. The ideal depth depends on the project size you're working on.

* **Bad structure**

```
project/
└── src/
    └── modules/
        └── auth/
            └── core/
                ├── login.c
                ├── login.h
                └── utils.c
        └── database/
            └── drivers/
                ├── db.c
                └── db.h
        └── network/
            └── protocols/
                ├── http.c
                └── http.h
```

* **Good Structure**

```
project/
└── src/
    └── auth/
        ├── login.c
        ├── login.h
        └── utils.c
    └── database/
        ├── db.c
        └── db.h
    └── network/
        ├── http.c
        └── http.h
```

---

> **Note:** The file and directory naming conventions in this section are inspired by [Files and Directories](https://www.arsnl.dev/guidelines/files-and-directories).

---

## Branch Naming Conventions

Consistent Git branch naming conventions provide clarity about the work done in a specific branch. Please follow these practices when naming your branches.

### Basic Rules

1. **Lowercase and Hyphen-separated:** Use lowercase letters and separate words with hyphens. Examples: `feature/new-feature`, `bugfix/bug-to-be-fixed`
2. **Alphanumeric Characters Only:** Branch names should contain only lowercase letters, numbers, and hyphens. Avoid uppercase letters, spaces, underscores, and special characters.
3. **Descriptive and Concise:** Choose a name that clearly describes the work done on the branch.

### Branch Prefixes

Branch prefixes clarify the purpose of each branch at a glance. Use the following prefixes for different types of work:

1. **Feature Branches (`feature/`):** For developing new features. Example: `feature/new-feature`
2. **Bugfix Branches (`bugfix/`):** For fixing bugs and issues. Example: `bugfix/bug-to-be-fixed`
3. **Documentation Branches (`docs/`):** For writing or updating documentation. Example: `docs/api-reference`
4. **Release Branches (`release/`):** For preparing production releases. Example: `release/v1.0.0`

### Issue-Specific Branches

When working on a specific issue, include the issue number in your branch name to create a clear link between the branch and the issue.

**Format:** `[prefix]/issue-[number]-[description]`

**Example:** `feature/issue-42-add-new-feature`

When you open a pull request for this branch, mention the issue number in the PR description using `Closes #[number]` or `Fixes #[number]`. This will automatically link the pull request to the issue and close it when the PR is merged.

### Branch Name Examples

* `feature/issue-42-add-new-feature`
* `bugfix/issue-57-fix`
* `feature/new-feature`
* `release/v2.0.1`

---

> **Note:** The branch naming conventions in this section are inspired by [Git Branch Naming Conventions - A Cheatsheet](https://medium.com/@abhay.pixolo/naming-conventions-for-git-branches-a-cheatsheet-8549feca2534).

---

## Commit Message Conventions

### Basic Rules

1. **Lowercase:** Use lowercase letters. Examples: `feat: added new feature somewhere`, `fix: fixed a bug somewhere`
2. **Descriptive and Concise:** Describe the commit as precisely as possible.

### Commit Message Prefixes

Commit message prefixes clarify the purpose of each commit at a glance. Use the following prefixes for different types of commits:

1. **Feature Commit (`feat:`):** For developing new features. Example: `feat: added new feature somewhere`
2. **Bugfix Commit (`fix:`):** For fixing bugs and issues. Example: `fix: fixed a bug somewhere`
3. **Documentation Commit (`docs:`):** For writing or updating documentation. Example: `docs: api-reference`
4. **Merge Commit (`Merge branch '<branch name>'`):** For merging a branch. Example: `Merge branch 'Bugfix'`

### Scope

Indicating the scope is useful when you want to show which part of the program you worked on.

1. The scope must be indicated between parentheses right after the type of commit. Example: `feat(api): new feature concerning the API`
2. The scope can be anything as long as it is descriptive and concise.
3. The scope is optional.

### Important Changes

If you are introducing a breaking change, indicate it clearly in the commit message. 

A breaking change is a modification that is not backward-compatible and may require updates from users or downstream systems (for example, renaming an API field, changing a function signature, or removing an endpoint).

1. Use an exclamation point (`!`) after the type of commit (and scope if present). Examples: `feat(api)!: new feature concerning the API`, `feat!: new feature`.
2. Optionally add a footer to describe the breaking change in detail. Example: `BREAKING CHANGE: describe the impact and migration steps`.

### Commit Message Examples

* `feat(ui): add user profile page`
* `fix(auth): handle expired refresh tokens`
* `docs: update installation guide`
* `feat(api)!: rename user id field` + `BREAKING CHANGE: update clients to use user_id`
* `Merge branch 'feature/new-feature'`

---

> **Note:** The commit message conventions in this section are inspired by [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).

---

## Issue Conventions

When creating an issue, you must use one of the available issue templates. These templates ensure that all necessary information is provided to properly address the issue.

### Issue Templates

Two issue templates are available:

1. **Bug Report:** Use this template to report a problem or unexpected behavior
2. **Feature Request:** Use this template to propose a new capability or improvement

### How to Create an Issue

1. Go to the **Issues** tab on GitHub
2. Click **New issue**
3. Select the appropriate template (bug report or feature request)
4. Fill in all **required fields** marked with an asterisk
5. Complete optional fields when relevant (screenshots, assignees, inspiration sources)
6. Submit the issue

### Issue Title Guidelines

The issue title should follow these rules:

1. **Clear and Concise:** Summarize the issue in a few words
2. **Descriptive:** Indicate what the issue is about without opening it
3. **No Prefixes Required:** The template already categorizes the issue type

### Filling Templates

When filling an issue template:

1. **Be Specific:** Provide clear and detailed information
2. **Include Examples:** Show the problem or expected behavior with examples
3. **Add Context:** Include relevant screenshots, error messages, or links
4. **Mention Sources:** If inspired by external content, reference it in the "Inspiration" field
5. **Suggest Assignees:** If you know who could work on it, mention them

---

> **Note:** The issue conventions in this section are inspired by [these project templates](https://github.com/DevLeonardoCommunity/github-stats).

---

## Pull Request Conventions

All pull requests must follow the project template. The template standardizes reviews and ensures nothing important is missing.

### Using the PR Template

1. Open a pull request and let GitHub load the template automatically
2. Read the visible instructions and remove the lines marked **REMOVE THESE LINES** before submitting
3. Fill in every section of the template
4. Do not delete sections, only remove the instructional lines
5. Optionally, you can add sections if you think it is necessary

### Required Content

1. **Summary:** What changed and why
2. **Issues:** Link the issue(s) using `Fixes #123` or a list under **Fixes**
3. **Type of change:** Check at least one box
4. **Testing:** Describe how you tested or state `Not tested` with a reason
5. **Checklist:** Confirm each item or explain why it does not apply

### Title Guidelines

1. **Clear and concise:** Explain the change in a short sentence
2. **Action-oriented:** Start with a verb (e.g., “Add”, “Fix”, “Update”)

### Good Practices

* Keep the PR focused on a single goal
* Add screenshots or logs when relevant

---

> **Note:** The Pull Request conventions in this section are inspired by [Setting Up a Pull Request Template for your GitHub Repo](https://vijayasimhabr.medium.com/setting-up-a-pull-request-template-for-your-github-repo-352c3a538a2c) and [Creating a pull request template for your repository](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository).

---
