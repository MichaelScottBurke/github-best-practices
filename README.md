# GitHub for designers

A github best practice cheat sheet for designers and new developers who want **clear, repeatable habits** working with GitHub. This covers core concepts, daily workflows, and good developer hygiene — useful whether you’re collaborating with others or working alone.

---

## Core Concepts
- **Repository (repo)** = your project folder tracked by Git.
- **Commit** = a snapshot of your changes.
- **Push** = send your changes to GitHub.
- **Pull** = get the latest changes from GitHub.
- **Branch** = a separate version of your project (like a sandbox).
- **Merge** = combine changes from one branch into another.

---

## Terminal Basics

### Setup (One-Time)
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### Start a New Project
```bash
mkdir my-project
cd my-project
git init
```

### Track & Save Changes
```bash
git add .
git commit -m "Initial commit"
```

### Connect to GitHub
```bash
git remote add origin https://github.com/yourusername/repo-name.git
git push -u origin main
```

### Get Latest Updates
```bash
git pull origin main
```

### Work in a Branch
```bash
git checkout -b feature-branch-name
```

### Merge Branch
```bash
git checkout main
git merge feature-branch-name
```

### Delete Branch
```bash
git branch -d feature-branch-name
```

---

## GitHub desktop basics
Github desktop is an app that lets you focus on the git workflow without having to learn terminal commands

- **New Repo** → File → New Repository → Create.
- **Publish** → Click *Publish Repository*.
- **Commit** → Add summary → *Commit to main*.
- **Sync** → Push = send, Pull = receive.
- **Branching** → Current Branch → New Branch → Commit changes → Merge.

---

## Clone vs Fork

- **Clone** → *“Work with this repo directly.”* → For team projects.
- **Fork** → *“Make my own copy.”* → For open-source or experiments.

---

## Branching Best Practices

1. **Always work in a branch**
   ```bash
   git checkout -b feature/update-homepage
   ```
2. **Use clear names**
   - `feature/add-login-form`
   - `fix/navbar-alignment`
3. **One task = one branch**
4. **Commit often with clear messages**
   - "Add hero section"
   - "Fix typo in footer"
5. **Merge back to main** when done
6. **Delete merged branches** to stay clean

---

## Daily Best Practices (Developer Hygiene)

Whether you're working alone or on a team, follow these steps each workday:

### 🔄 Morning Routine
1. **Start fresh**
   ```bash
   git checkout main
   git pull origin main
   ```
2. **Update your feature branch**
   ```bash
   git checkout feature/my-task
   git merge main
   ```

### While Working
- Commit frequently (small, clear commits).
- Write meaningful commit messages.
- Keep your branch focused on one task.

### End of Day
1. Save work:
   ```bash
   git add .
   git commit -m "WIP: progress on task"
   ```
2. Push your branch:
   ```bash
   git push origin feature/my-task
   ```
3. Make sure `main` is clean and up-to-date.

---

## Pull Requests (PRs)

Pull Requests (PRs) are how changes in one branch are proposed, reviewed, and merged into another branch (usually `main`). Even if you’re working solo, using PRs builds good habits and gives you a history of changes.

### As the Requestor (Author)
1. **Finish your branch work**
   - Commit and push all changes.
   - Ensure your branch is up to date with `main`.
   ```bash
   git checkout main
   git pull origin main
   git checkout feature/my-task
   git merge main
   ```

2. **Open a Pull Request**
   - Go to GitHub → your repo.
   - Click **Compare & Pull Request**.
   - Write a **clear title** (e.g., “Fix: Navbar alignment issue”).
   - Add a **description** (what/why, any context).
   - Assign reviewers (if applicable).

3. **Respond to Feedback**
   - Make edits in your branch.
   - Push new commits; they will automatically appear in the PR.

4. **Mark Ready & Merge**
   - Once approved (or confident as a solo dev), merge to `main`.
   - Choose **Squash and Merge** (recommended for clean history).
   - Delete the branch afterward.

---

### As the Reviewer
1. **Read the Description**
   - Understand what the author is changing and why.

2. **Check the Code**
   - Look for clarity, consistency, and whether it solves the stated problem.
   - Ensure no obvious errors or broken files.

3. **Test Locally (if needed)**
   ```bash
   git fetch origin feature/their-branch
   git checkout feature/their-branch
   ```
   Run the project and confirm changes work.

4. **Give Feedback**
   - Use **comments** for suggestions.
   - Approve if good, or request changes.

5. **Approve & Merge (if allowed)**
   - Click **Approve**.
   - Merge into `main` following team conventions.

---

### Why Pull Requests Matter
- Creates a review step before code goes into `main`.
- Documents *why* a change was made.
- Builds team trust (or future-you trust, if working solo).
- Helps keep `main` stable and reliable.

---

## Designer-friendly summary

| Action       | You’re saying…                      | Typical Use |
|--------------|-------------------------------------|-------------|
| **Clone**    | “I want to work *with* this repo.” | Team work   |
| **Fork**     | “I want my *own* copy to play with.”| Experiments |
| **Branch**   | “I’ll work on this task separately.”| Features/fixes |
| **Commit**   | “Here’s a snapshot of my progress.” | Save work   |
| **Push**     | “Send my changes to GitHub.”        | Share work  |
| **Pull**     | “Get the latest updates.”           | Stay synced |
| **PR**       | “Please review and merge my work.”  | Collaboration |

---

## Flow

1. Pull latest changes → 2. Create branch → 3. Do work → 4. Commit often → 5. Push → 6. Open PR → 7. Merge → 8. Delete branch
