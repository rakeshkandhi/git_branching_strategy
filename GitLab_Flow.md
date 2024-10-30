# GitLab Flow Branching Strategy

### Overview
- **Purpose**: Combines elements of Git Flow and GitHub Flow, supporting multiple environments like `development`, `uat`, and `production`.
- **When to Use**: Suitable for projects with multiple testing environments.

### Workflow Steps
1. **Create Feature Branches** from `development`.
2. **Raise Merge Requests** to `development` for integration.
3. **Promote Features to `uat` and `production** selectively.

### Git CLI Commands
- **Create a Feature Branch**:
  ```bash
  git checkout development
  git pull origin development
  git checkout -b feature/feature-name
  ```
- **Merge Feature into `development`**:
  ```bash
  git checkout development
  git merge feature/feature-name
  git push origin development
  ```
- **Promote Feature from `development` to `uat`**:
  ```bash
  git checkout uat
  git merge development
  git push origin uat
  ```
- **Promote Feature from `uat` to `production`**:
  ```bash
  git checkout production
  git merge uat
  git push origin production
  ```

### Pros and Cons
| Pros | Cons |
|------|------|
| Supports multiple environments | Complex with multiple environments |
| Flexibility in promoting features | Higher coordination effort required |
| Structured approach for continuous delivery | Requires selective cherry-picking |
