# Git & GitHub Workflow Tutorial

This tutorial provides a clear, step-by-step workflow for using Git and GitHub in the Private Bee project. It covers setup, branching, commits, pull requests, and collaboration best practices so you can contribute safely and consistently.

## Table of contents

- [Conventions](#conventions)
- [General Git Best Practices](#general-git-best-practices)
- [Setup Git in command line](#setup-git-in-command-line)
    - [1. Install Git](#1-install-git)
    - [2. Configure Git](#2-configure-git)
    - [3. Verify your Git configuration](#3-verify-your-git-configuration)
- [Setup your SSH key](#setup-your-ssh-key)
    - [1. Generating a new SSH key](#1-generating-a-new-ssh-key)
    - [2. Copy your SSH key](#2-copy-your-ssh-key)
    - [3. Add the SSH key to GitHub](#3-add-the-ssh-key-to-github)
    - [4. Test your SSH connection](#4-test-your-ssh-connection)
- [Cloning the Repository](#cloning-the-repository)
- [Creating a Branch](#creating-a-branch)
    - [Command line](#command-line)
    - [Web interface](#web-interface)
- [Making Changes and Committing](#making-changes-and-committing)
- [Pushing your Branch](#pushing-your-branch)
    - [First Push of a New Branch](#first-push-of-a-new-branch)
    - [Pushing New Commits](#pushing-new-commits)
    - [Verifying on GitHub](#verifying-on-github)
- [Making changes via the web interface](#making-changes-via-the-web-interface)
    - [Add a file](#add-a-file)
    - [Modify a file](#modify-a-file)
    - [Delete a file](#delete-a-file)
- [Opening a pull request](#opening-a-pull-request)
    - [Opening a Pull Request from GitHub](#opening-a-pull-request-from-github)
    - [Filling the Pull Request](#filling-the-pull-request)
    - [After creating the Pull Request](#after-creating-the-pull-request)
    - [Summary](#summary)
- [Pulling Latest Changes](#pulling-latest-changes)
    - [Pulling Changes from GitHub](#pulling-changes-from-github)
    - [When Should you Pull?](#when-should-you-pull)
- [Resolving Merge Conflicts](#resolving-merge-conflicts)
    - [When do Conflicts occur?](#when-do-conflicts-occur)
    - [What happens during a Conflict?](#what-happens-during-a-conflict)
    - [Understanding Conflict Markers](#understanding-conflict-markers)
    - [Resolving the Conflict](#resolving-the-conflict)
    - [After Resolving the Conflict](#after-resolving-the-conflict)
- [Working with Issues](#working-with-issues)
    - [Viewing Existing Issues](#viewing-existing-issues)
    - [Creating an Issue](#creating-an-issue)
    - [Working on an Issue](#working-on-an-issue)
    - [Linking a Pull Request to an Issue](#linking-a-pull-request-to-an-issue)
    - [Updating and closing the Issue](#updating-and-closing-the-issue)

## Conventions

The coding conventions for this project are described in [CONVENTIONS.md](./CONVENTIONS.md). Please read them before starting to work on the project.

---

## Complete Git and GitHub Tutorial

### Setup Git in command line

Git will allow you to efficiently work on any project that is part of Private Bee. Please follow the instructions below to install Git and configure it on your computer.

#### 1. Install Git

* **Linux**

Open the terminal and run:
```bash
sudo apt update
sudo apt install git
```

Check the installation:
```bash
git --version
```

You should see a message with your git version.

* **macOS**

If you have **Homebrew** installed:
```bash
brew install git
```

If not, Git can be installed by installing Xcode Command Line Tools:
```bash
xcode-select --install
```

Check the installation:
```bash
git --version
```

You should see a message with your git version.

* **Windows**

Go to the official [Git website](https://git-scm.com/install/windows) and download Git for Windows.

Then install it with default options.

#### 2. Configure Git

Once Git is installed, you need to set your **name** and **email**, which will be used for your commmits.

You can choose any name you want. For the email, it is recommended to use the email associated with your GitHub account, so your commits can be linked to your profile.

Run the following commands:
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

#### 3. Verify your Git configuration

To confirm that everything is set correctly, type the following command:
```bash
git config --global --list
```

You should see output similar to:
```ini
user.name=Your Name
user.email=your_email@example.com
```

Once Git is installed and configured, you can proceed to generate your SSH key.

---

### Setup your SSH key

Setting up an SSH key allows you to work on a Git repository using the command line. This step is not mandatory. Indeed, you can also contribute via the web interface. But if you plan to make significant changes, it is recommended to set up an SSH key.

After installing Git and setting it up, you should **setup your SSH key**. To do so, and if you haven't already set up an SSH key, please complete the following steps.

If you already have set up an SSH key, you can reuse it or follow the steps to replace it.

#### 1. Generating a new SSH key

Open your terminal and **paste the text below**, replacing the email used in the example with your GitHub email address.

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

This creates a new SSH key, using the provided email as a label.

When you're prompted to "Enter a file in which to save the key", you can **press Enter** to accept the default file location.

Then you will be prompted to type a secure passphrase. It is recommended to use a passphrase, but you can leave it empty if you wish.

#### 2. Copy your SSH key

Now that your SSH key is generated, you need to copy it to add it to GitHub.

* **Linux / Mac:**
```bash
cat ~/.ssh/id_ed25519.pub
```

* **Windows (Powershell):**
```powershell
type $env:USERPROFILE\.ssh\id_ed25519.pub
```

Copy the **entire output**. It should look like:

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICk1... your_email@example.com
```

```
⚠️ Never share your private key (id_ed25519), only the public key (id_ed25519.pub).
```

#### 3. Add the SSH key to GitHub

1. Go to **GitHub** → **Settings** → **SSH and GPG keys** → **New SSH key**.
2. Give your key a **Title** (like "Laptop" or "Work PC").
3. Leave the key type as **Authentication Key** and **paste your SSH key in the box**.
4. Click **Add SSH key**.

#### 4. Test your SSH connection

To make sure everything works, run:

```bash
ssh -T git@github.com
```

You should see a message confirming your identity.

You are now ready to securely contribute to GitHub repositories!

---

### Cloning the Repository

After setting up your SSH key, cloning a repository allows you to work on it locally on your computer using command lines.  
While you can also contribute via the GitHub web interface, cloning is recommended if you plan to make significant changes.

First, go to the repository you want to clone on GitHub.

Then, click on the green **<> Code** button, select the **SSH tab**, and copy the link.

If your SSH key is correctly set up and Git is installed, run the following command:
```bash
git clone [COPIED LINK]
```

Now, move inside the cloned repository directory:
```bash
cd [REPOSITORY]
```

Example:
```bash
git clone git@github.com:username/repository.git
cd repository
```

---

### Creating a Branch

Whenever you plan to make changes to a project, you should **create a branch**.  
Working on a separate branch allows you to develop new features or fix bugs **without directly affecting the main branch**.

Once your changes are ready, you can commit them and open a pull request to merge your branch into the main branch. 

In this section, you will learn how to create a branch and work on it locally.

---

#### Command line

First, make sure you are inside the project repository:
```bash
cd [REPOSITORY]
```

Before creating a new branch, it is good practice to check which branch you are currently on:
```bash
git branch
```

The branch with an asterisk (`*`) is your current branch (usually **main**).

To create a new branch, use:
```bash
git branch [BRANCH_NAME]
```

---

Don't forget to follow the [branch naming conventions](./CONVENTIONS.md#branch-naming-conventions).

For example, your command can look like the following:
```bash
git branch feature/issue-42-add-new-feature
git branch bugfix/fix
```

---

You can use the **`git branch`** command again to see that your branch has correctly been created.

At this point:
* The branch has been created
* You are still on the main branch
* No changes are made on the project yet

To start working on your new branch, you must switch to it:
```bash
git checkout [BRANCH_NAME]
```

For example:
```bash
git checkout feature/issue-42-add-new-feature
```

You can use the **`git branch`** command again to see that you are on your new branch. The asterisk (`*`) should now be next to your new branch name.

From this moment:
* All your changes will apply **only to this branch**
* The main branch will **remain untouched**

You are now ready to make changes. In the following sections, you will learn to commit changes, push your commits and open a pull request.

---

#### Web interface

It is also possible to create a branch directly from the GitHub web interface.

To do so, go to your project repository on GitHub.

At the top left of the file list, click on the branch selector (usually showing **main**).

In the search field, type the name of your new branch and press **Enter** or click on **“Create branch: [BRANCH_NAME] from main”**.

Your branch is now created on GitHub. You can work on it directly using the GitHub web interface, or work on it locally on your machine.

If you want to work on this branch on your local machine, you must first retrieve it. Use the **`git pull`** command as explained in the [Pulling Latest Changes](#pulling-latest-changes) section.

You can now switch to the branch you created:
```bash
git checkout [BRANCH_NAME]
```

You can verify that the branch is available locally:
```bash
git branch
```

The asterisk (`*`) should now be next to your branch name.

From this point, you can work on the branch exactly like any other local branch.

Also, when selecting a branch on GitHub, you can see how far ahead or behind it is compared to the branch it was created from. This information is useful to know whether you need to push your changes or pull updates from another branch.

---

### Making Changes and Committing

Now that you've created your own branch, you are ready to make changes and commmit them.

To commit changes you need to follow these two steps:
* Add files that need to be commited
* Commit the files with a message

To add files to your commit, use the **`git add`** command.
You can either add all files or manually add the files you want.

To add all modified files, run:
```bash
git add .
```

To manually add specific files, run:
```bash
git add [FILE_NAME_1] [FILE_NAME_2] [FILE_NAME_3] ...
```

After adding the files, commit them by running:
```bash
git commit -m "COMMIT MESSAGE"
```

Don't forget to follow the [File and Directory Naming Conventions](./CONVENTIONS.md#file-and-directory-naming-conventions-and-structure) and the [Commit Message Conventions](./CONVENTIONS.md#commit-message-conventions).

Your changes are now saved in your branch.
In the next sections, you will learn to push your commits to GitHub and open a pull request.

---

### Pushing your Branch

Before pushing your changes, it is important to make sure that your branch is up to date with the remote repository.  
Pulling the latest changes first helps avoid conflicts and push errors.

For more details, see:
- [Pulling Latest Changes](#pulling-latest-changes)
- [Resolving Merge Conflicts](#resolving-merge-conflicts)

If other contributors have pushed changes to the same branch or to the base branch, you should run:
```bash
git pull
```

Once your branch is up to date, you can safely push your commits.

---

Once you have committed your changes on your branch, you need to **push** them to GitHub.  
Pushing uploads your local commits to the remote repository so that others can see them and so you can open a pull request.

Before pushing, make sure you are on the correct branch:
```bash
git branch
```

The branch with an asterisk `(*)` is the branch that will be pushed.

---

#### First Push of a New Branch

If this is the first time you push this branch to GitHub, run:
```bash
git push -u origin [BRANCH_NAME]
```

For example, your command can look like the following:
```bash
git push -u origin feature/issue-42-add-new-feature
git push -u origin bugfix/fix
```

This command:
* Pushes your branch to the remote repository (`origin`)
* Links your local branch to the remote branch
* Allows you to use `git push` without extra options next time

---

#### Pushing New Commits

After the branch has been pushed once, you can push new commits by simply running:
```bash
git push
```

Your commits are now available on GitHub.

---

#### Verifying on GitHub

Afet pushing, go to your repository on GitHub.
You should see your branch listed, along with a suggestion to open a **pull request**.

Your changes are now safely stored on GitHub and ready to be reviewed and merged.

---

### Making changes via the web interface

If you want, you can also make changes directly via the GitHub web interface. This is equivalent to committing and pushing changes at the same time.

---

#### Add a file

To add a file, click on the **`Add file`** button. Then, you can choose between **creating a new file** or **uploading an existing one**.

If you choose to **create a file**, a text editor will open. Enter the file name and its content, then click on the **`Commit changes...`** button, add a commit message and an optional description, and commit the file.

If you choose to **upload a file**, a new page will open where you can upload one or more files. Add a commit message and an optional description, and commit the file.

Don't forget to follow the [File and Directory Naming Conventions](./CONVENTIONS.md#file-and-directory-naming-conventions-and-structure) and the [Commit Message Conventions](./CONVENTIONS.md#commit-message-conventions).

---

#### Modify a file

To modify an existing file, click on the file, then click on the **Pen** icon on the right side of the page and make your changes.

Finally, click on the **`Commit changes...`** button, add a commit message and an optional description, and commit the changes.

---

#### Delete a file

To delete a file, click on the file, then click on the three dots **``...``** button at the top right of the page. Scroll down and click on the **`Delete file`** button.

Then, click on the **`Commit changes...`** button, add a commit message and an optional description, and commit the changes.

---

### Opening a pull request

Once you have pushed your branch to GitHub, you can open a **pull request**.  
A pull request allows you to propose your changes to be merged into the main branch and to request a review from other contributors.

---

#### Opening a Pull Request from GitHub

Go to the project repository on GitHub.

After pushing your branch, GitHub will usually display a message suggesting to **`Compare & pull request`**. Click on this button.

Alternatively, you can:
* Click on the **``Pull requests``** tab
* Click on **``New pull request``**
* Select your branch as the **compare** branch and **main** as the **base** branch

---

#### Filling the Pull Request

When you open a pull request, GitHub will automatically load the project's **pull request template** (see [.github/PULL_REQUEST_TEMPLATE.md](./.github/PULL_REQUEST_TEMPLATE.md)).

Follow these steps:

1. Make sure the **base branch** is **main**
2. Make sure the **compare branch** is your branch
3. GitHub will load the template with guided sections
4. Follow the template instructions:
   - Remove the lines marked **REMOVE THESE LINES**
   - Fill in each section (summary, type of change, testing, checklist)
   - Add any additional information if needed
5. Do not delete sections, only remove the instructional lines

Refer to the [Pull Request Conventions](./CONVENTIONS.md#pull-request-conventions) for detailed guidance.

When ready, click on **``Create pull request``**.

---

#### After creating the Pull Request

Your pull request is now open.

From this point:
* Other contributors can review your changes
* You may be asked to make modifications
* You can **push new commits** to the **same branch**, and the pull request will **update automatically**

Once approved, the pull request can be merged into the main branch.

#### Summary

* A pull request proposes changes from one branch to another
* It allows review and discussion before merging
* It helps keep the main branch stable and clean

### Pulling Latest Changes

When working on a project with other contributors, the remote repository may change while you are working.  
Pulling the latest changes allows you to update your local repository with the most recent version from GitHub.

Before pulling, make sure you are inside the project repository and check the branch you are currently on:
```bash
cd [REPOSITORY]
git branch
```

The branch with an asterisk (**``*``**) is the branch that will be updated.

---

#### Pulling Changes from GitHub

To retrieve the latest changes from GitHub, run:
```bash
git pull
```

This command:
* Fetches the **lastest changes** from the remote repository
* **Merges them** into your current local branch

If no changes are available, Git will indicate that your branch is **already up to date**.

---

#### When Should you Pull?

You should pull:
* Before starting to work on a branch
* Before creating a new branch
* Before opening a pull request
* When GitHub shows that your branch is behind the base branch

Pulling regularly helps avoid conflicts and keeps your work up to date.

---

### Resolving Merge Conflicts

When pulling changes from GitHub, Git may sometimes report a **merge conflict**.  
This happens when the same part of a file has been modified both locally and remotely, and Git cannot decide which version to keep automatically.

Merge conflicts are **normal** in collaborative projects and can be resolved safely.

---

#### When do Conflicts occur?

Conflicts usually occur when:
* Two people modify the same file at the same time
* The same lines of code or text are changed differently
* You pull changes that affect files you have modified locally

---

#### What happens during a Conflict?

When a conflict occurs:
* Git stops the merge process
* The affected files are marked as conflicted
* Git will display a message explaining which files have conflicts

You can see the list of conflicted files by running:
```bash
git status
```

---

#### Understanding Conflict Markers 

Open a conflicted file in a text editor.

<!-- Please do not remove the example below -->

You will see markers like these:
```
<<<<<<< HEAD
[Your local changes]
=======
[Incoming changes from GitHub]
>>>>>>> branch-name
```

* The section between ``<<<<<<< HEAD`` and ``=======`` is your local version
* The section between ``=======`` and ``>>>>>>>`` is the remote version
* You must decide what to keep

---

#### Resolving the Conflict

To resolve the conflict:
1. Edit the file and choose which changes to keep
    * Keep one version
    * Or manually combine both versions
2. Remove all conflict markers (``<<<<<<<``, ``=======``, ``>>>>>>>``)
3. Save the file

Once the conflict is resolved, add the file and commit the result:
```bash
git add [FILE_NAME]
git commit -m "Resolve merge conflict"
```

---

#### After Resolving the Conflict

After committing:
* The merge is completed
* Your branch is now up to date
* You can continue working normally

If you were pulling changes before pushing or opening a pull request, you can now continue that process.

### Working with Issues

Issues are used to **track tasks, bugs, and feature requests** in a project.  
They help organize work, discuss changes, and coordinate between contributors.

An issue can describe:
* A bug to fix
* A feature to implement
* An improvement or task to complete
* A question or discussion topic

---

#### Viewing Existing Issues

To view issues, go to your repository on GitHub and click on the **Issues** tab.

Before creating a new issue, make sure that:
- A similar issue does not already exist
- The problem or request has not already been addressed

---

#### Creating an Issue

To create a new issue:

1. Go to the **``Issues``** tab
2. Click on **``New issue``**
3. GitHub will show available **issue templates** (bug report or feature request)
4. Select the template that matches your issue type
5. Fill in the template fields with the required information
6. Optionally, assign the issue to someone and add labels

Refer to the [Issue Conventions](./CONVENTIONS.md#issue-conventions) for detailed guidance on what to include in each field.

Then, click on **``Create``**.

---

#### Working on an Issue

When you start working on an issue:
- Assign the issue to yourself (if allowed)
- Create a new branch related to the issue

It is recommended to name your branch using the issue number, for example:
```text
issue-42-fix-bug
```

This helps keep a clear link between the issue and the code changes.

---

#### Linking a Pull Request to an Issue

When opening a pull request related to an issue, mention the issue number in the pull request description.

For example:
```text
Closes #42
```

This will:
* Automatically link the pull request to the issue
* Close the issue when the pull request is merged

---

#### Updating and closing the Issue

While working on an issue:
* Use comments to give updates or ask questions
* Share progress or difficulties

Once the work is completed and merged:
* The issue is usually closed automatically (if linked)
* Or it can be closed manually

---
