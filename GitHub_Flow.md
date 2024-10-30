# GitHub Flow Branching Strategy

### Overview
- **Purpose**: A simpler branching strategy than Git Flow, ideal for continuous delivery.
- **When to Use**: Suited for small to medium projects with high deployment frequency, such as SaaS applications.

### Workflow Steps
1. **Create a Feature Branch** from `main` for each feature.
2. **Raise Pull Requests** for code review and integration into `main`.
3. **Deploy Directly from `main`** after testing.

### Git CLI Commands
- **Create a Feature Branch**:
  ```bash
  git checkout main
  git pull origin main
  git checkout -b feature/feature-name
  ```
- **Open a Pull Request** on GitHub to `main`.
- **Merge Feature into `main`** after approval:
  ```bash
  git checkout main
  git merge feature/feature-name
  git push origin main
  ```

### Pros and Cons
| Pros | Cons |
|------|------|
| Simple workflow with fewer branches | Not ideal for projects needing multiple environments |
| Direct deployment to production | Limited to a single environment |
| Minimal overhead | Challenging to manage hotfixes independently |
