# 🔒 Daily Git Workflow Checklist (Interns & Developers)

## ✅ Start of Day
1. **Pull latest changes:**
   ```bash
   git pull --rebase origin <your-branch>
   ```
   - Keeps your local branch up to date
   - Avoids unnecessary merge commits
   - ⚠️ If you encounter conflicts, resolve them as prompted, then continue the rebase with:
     ```bash
     git rebase --continue
     ```
   - If unsure, ask a teammate or mentor for help with conflicts.

2. **Check repo status:**
   ```bash
   git status
   ```

3. **Branch naming:**
   - Use descriptive branch names, e.g., `feature/login-page`, `bugfix/typo-in-readme`, `chore/update-deps`.

---

## 💻 During Work
- Make **frequent commits**, ideally after every significant logical change.
- **Follow commit message conventions:**
  - `feat: add new parser`
  - `fix: correct edge case bug`
  - `refactor: clean up utility functions`
  - `docs: update README`
  - `test: add unit tests for parser`
  - `chore: update dependencies`
- For more details, see [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).
- **Run automated checks** (tests, linters) before committing:
  ```bash
  # Example for Node.js
  npm test
  npm run lint
  # Example for Python
  pytest
  flake8 .
  ```
- **Backup uncommitted work:**
  - Use `git stash` to temporarily save changes:
    ```bash
    git stash
    # To retrieve later:
    git stash pop
    ```
  - Or manually copy files to a safe location.

---

## 🛑 Before You Leave (Most Important)
Run all commands from the **root directory** of your repository.

1. **Check working directory:**
   ```bash
   git status
   ```

2. **Stage all changes (including deletions):**
   ```bash
   git add -A
   ```

3. **Review staged files:**
   ```bash
   git status
   ```

4. **Commit:**
   ```bash
   git commit -m "Your clear and descriptive message"
   ```
   - See commit message conventions above.

5. **Push to remote:**
   ```bash
   git push origin <your-branch>
   ```
   - ⚠️ If you encounter a push error, pull/rebase first, resolve any conflicts, then push again.

6. **Code review:**
   - If your team uses Pull Requests or Merge Requests, create one and request a review.
   - Review others' code if assigned.

7. **Verify your latest commit is visible on the remote:**
   - Check on GitHub/GitLab/Bitbucket web UI.
   - Confirm your commit hash and message appear as expected.

---

## ⚠️ Pre-Reset / End of Week
- Confirm **all changes are pushed**
- If needed, backup uncommitted work separately using:
  ```bash
  git stash
  ```
  or manually copy files

---

## 🔄 Merge vs. Rebase
- **Rebase** (recommended for feature branches):
  - Keeps history linear and clean
  - Use `git pull --rebase` to avoid unnecessary merge commits
- **Merge** (for integrating long-lived branches):
  - Use when combining major features or releases
  - Creates a merge commit, preserving full branch history

---

## 👀 Tips & Common Pitfalls
- Don’t assume uncommitted changes will survive system resets
- Use `git add -A` to ensure **all** changes are staged, including file deletions
- Always run `git status` before and after staging
- **Common mistakes:**
  - Forgetting to pull before pushing
  - Not staging deletions
  - Pushing to the wrong branch
  - Not resolving conflicts fully
- If you’re unsure, ask for help early!

---

## 🧩 Visual Guide
- ✅ = Start of Day
- 💻 = During Work
- 🛑 = Before You Leave
- ⚠️ = Pre-Reset / End of Week
- 🔄 = Merge vs. Rebase
- 👀 = Tips & Common Pitfalls

---

Happy Coding! 🚀
