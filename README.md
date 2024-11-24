<ins>This is not the real project readme, this is for our organization, we'll change it afterwards</ins>

# LLMAgentBZR




# 1. Organizing our WorkFlow

## 1.1 Comparison of Branching Strategies

| **Aspect**                 | **GitFlow**            | **Feature Branch**         | **Trunk-Based Development** |
|----------------------------|------------------------|----------------------------|-----------------------------|
| **Complexity**             | High                   | Moderate                   | Low                         |
| **Ideal Team Size**        | Medium to Large        | Small to Medium            | Small to Large              |
| **Deployment Frequency**   | Scheduled              | Varies                     | Continuous                  |
| **Merge Conflicts**        | Minimal with process   | Moderate                   | Frequent (if not managed)   |
| **Best For**               | Release-driven teams   | Teams focusing on features | Fast-paced teams with CI/CD |

We will be working with **Feature Branch** workflow: A simple and effective way to manage development tasks. It ensures each feature or bug fix is isolated, making collaboration easier and reducing conflicts.
## 1.2 How Does Feature Branch Workflow Works

1. **Start with `main`**:
   - All work begins from the main branch.

2. **Create a Feature Branch**:
   - When you start a new task, create a feature branch. This keeps your work isolated and avoids impacting others' work.
   - Naming convention: `feature/<task-name>` (e.g., `feature/user-login`).
     ```bash
     git checkout -b feature/<task-name>
     ```

3. **Work Locally**:
   - Make changes and commit regularly with meaningful messages.
     ```bash
     git add .
     git commit -m "Add user login functionality"
     ```

4. **Push Your Branch to GitHub**:
   - Keep your branch synced with the remote repository.
     ```bash
     git push origin feature/<task-name>
     ```

5. **Open a Pull Request (PR)**:
   - Once the feature is complete, open a PR to merge your branch into `main`.
   - Describe what your PR does and link any relevant issues (e.g., `Fixes #123`).

6. **Review & Merge**:
   - Your teammates will review the PR, suggest changes, and approve it.
   - After approval, merge your branch into the target branch.
   - Delete the feature branch after merging to keep the repository clean.

---

## 1.3 Best Practices for Feature Branch Workflow

1. **Keep Branches Short-Lived**:
   - Complete tasks quickly and merge regularly to avoid conflicts and reduce complexity.

2. **Write Descriptive Commit Messages**:
   - Good commit messages explain _what_ and _why_, not just _how_.
     ```bash
     git commit -m "Fix bug in login validation to handle empty passwords"
     ```

3. **Sync with `main` Regularly**:
   - Avoid large merge conflicts by pulling the latest changes frequently.
     ```bash
     git pull origin main
     ```

4. **Test Before Pushing**:
   - Run your code locally and ensure it works before pushing to GitHub.

5. **Follow Naming Conventions**:
   - Use consistent branch names like:
     - `feature/<task-name>` (e.g., `feature/add-login-page`)
     - `bugfix/<issue-description>` (e.g., `bugfix/fix-typo-homepage`)

6. **Use Pull Requests for Collaboration**:
   - Always open a PR for feedback and ensure someone reviews your code before merging.

7. **Keep PRs Focused**:
   - Limit each PR to one feature or fix. This makes it easier to review and test.

8. **Automate Testing**:
   - Set up Continuous Integration (CI) to automatically test your code when you push or open a PR.

9. **Clean Up After Merging**:
   - Delete feature branches after merging to keep the repository tidy:
     ```bash
     git branch -d feature/<task-name>
     ```

10. **Communicate with Your Team**:
    - Keep your team updated on your progress and any challenges you face.

---

## 1.4 Example Workflow

```bash
# 1. Start from the main branch
git checkout main
git pull origin main

# 2. Create a feature branch
git checkout -b feature/new-feature

# 3. Make changes and commit
git add .
git commit -m "Add new feature"

# 4. Push the feature branch
git push origin feature/new-feature

# 5. Open a Pull Request on GitHub
# 6. Merge after review and testing
# 7. Delete the local and remote feature branch
git branch -d feature/new-feature
git push origin --delete feature/new-feature
