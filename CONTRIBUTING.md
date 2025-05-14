# Guide to Participating in the Project

Thank you for your interest in participating in the project! To ensure effective and organized work, please follow these rules:

## Main Branch Rules

- **Main Branches:**
  - `main` — the main branch where only verified changes are merged.
  - `dev` — the branch for active development.

- **Direct Changes to Main are Prohibited:**
  - All changes to the `main` branch are accepted only through pull requests.
  - Direct pushes to the `main` branch are not allowed.

- **Working with the Dev Branch:**
  - You can freely push changes to the `dev` branch.

## How to Submit Changes to the Project

- **Creating a New Branch:**
  - To work on a new feature or fix, create a separate branch from `dev`:
    ```bash
    git checkout dev
    git checkout -b feature/my-new-feature
    ```

- **Submitting a Pull Request:**
  - After completing your work, create a pull request from your branch to the `main` branch.
  - Ensure that your change has been tested and meets the project's standards.
  - In the pull request description, clearly state the purpose of the change and link it to the relevant issue (if applicable).

## General Recommendations

- **Code Style:**
  - Follow the code formatting standards adopted in the project.

- **Commits:**
  - Write meaningful commit messages.

Thank you for adhering to these rules! This helps us maintain code quality and simplifies collaboration for the entire team.