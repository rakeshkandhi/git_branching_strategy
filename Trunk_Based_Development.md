# Trunk-Based Development Strategy

### Overview
- **Purpose**: Encourages rapid integration by maintaining a single branch (e.g., `development` or `main`).
- **When to Use**: Ideal for fast-paced, CI/CD environments with smaller teams.

### Workflow Steps
1. **Create Short-Lived Feature Branches** from the main branch.
2. **Integrate into `development` (or `main`) directly**.
3. **Deploy Continuously from `development` to production**.

### Git CLI Commands
- **Create a Feature Branch**:
  ```bash
  git checkout development
  git pull origin development
  git checkout -b feature/feature-name
  ```
- **Rebase Regularly** to keep updated:
  ```bash
  git fetch origin
  git rebase origin/development
  ```
- **Merge Feature back into `development`**:
  ```bash
  git checkout development
  git merge feature/feature-name
  git push origin development
  ```

### Pros and Cons
| Pros | Cons |
|------|------|
| Encourages fast integration with short-lived branches | Limited control over environment transitions |
| Best suited for continuous delivery | Requires robust CI/CD and automated testing |
| Fosters team collaboration | Less suitable for larger teams and complex projects |
