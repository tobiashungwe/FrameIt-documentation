# Version Control

## GitHub & GitLab Repositories

Our project utilizes both GitHub and GitLab for version control, with GitHub being the primary repository for public access, and GitLab used for additional collaboration and mirroring. The strategy ensures seamless development, collaboration, and tracking of changes across different platforms. Below are the key aspects of our version control strategy:

### 1. **Branching Strategy**
   - We follow a modified **Git Flow** strategy to keep development organized and allow multiple features to be developed in parallel.
   - **Main Branch** (`master` or `main`): This branch contains the latest stable version of the project. Only tested and reviewed code is merged here.
   - **Development Branch** (`dev`): This is the main branch where ongoing development happens. New features and fixes are merged here before reaching the main branch.
   - **Feature Branches**: Each feature is developed in a separate branch, following the naming convention:  
     `feature/(name of the milestone)/(name of the feature)`.  
     For example: `feature/milestone1/remove-deprecated-api-methods`.
   - **Hotfix Branches**: Hotfixes follow a similar structure:  
     `hotfix/(name of the milestone)/(description of the hotfix)`  
     For example: `hotfix/milestone2/fix-authentication-timeout`.
   - **Merge Requests (Pull Requests)**: Before merging any feature or hotfix into the `dev` or `main` branch, a merge request is created for review and testing. This ensures code quality, adheres to best practices, and allows for collaborative feedback.

### 2. **Commit Messages**
   - We use clear, structured, and consistent commit messages to ensure the project's history is easy to understand. The structure includes:
     - A concise summary of the changes (e.g., `feat: remove deprecated API methods`).
     - References to associated issues or tasks (e.g., `Closes #45` or `Relates to milestone1`).
   - **Example commit message**:  
     `feat: implement AI retraining option toggle (#87)`

### 3. **GitHub Actions & GitLab CI/CD Pipelines**
   - We leverage **GitHub Actions** for continuous integration on GitHub, ensuring code is automatically tested and built when pushed.
   - **GitLab CI/CD** is used on GitLab to maintain a mirrored version of the project, providing continuous integration for any additional workflows. This setup allows us to push code to both platforms and maintain seamless deployments.
   - Both CI/CD systems ensure that the code remains stable by running automated tests and performing checks on each branch push or merge request.

### 4. **Issue Tracking and Milestones**
   - **GitHub Issues** are used to track feature requests, bugs, and tasks, with each issue linked to specific branches and milestones. Each issue is organized by labels such as `feature`, `bug`, and `enhancement`.
   - Milestones help us organize issues into clear phases of development, corresponding to the project's major goals.
   - Example of issue assignment for a feature branch:  
     `feature/milestone1/gamification-layer`.

### 5. **Version Tagging**
   - **Version tagging** is done to mark significant releases or milestones in the project. Tags such as `v1.0`, `v2.0` represent major project milestones, new features, or client demos.
   - These tags are synchronized between both GitHub and GitLab, ensuring that all platforms reflect the same versioning.

### 6. **Handling Submodules**
   - Our project includes submodules like `FrameIt-documentation` and `FrameIt-sources`. These are managed across both GitHub and GitLab.
   - The submodule URLs are configured to point to the GitHub repository for easy access. We use the `git submodule` command to update, clone, and manage the submodules.
   - Although documentation is mirrored on GitLab for internal use, the primary reference URL for the submodules is on GitHub to ensure that users are directed to the correct repository.
   - **Pushing to Multiple Remotes**: While the submodule points to GitHub for easy navigation, we have both GitHub and GitLab configured as remotes, allowing us to push to both platforms using the following command:
     ```bash
     git push github dev
     git push gitlab dev
     ```

---

For more details on how version control is handled in the project or how specific features are tracked and merged, refer to the [Project Management](./project-management.md) section or return to the [Project Overview](../README.md).
