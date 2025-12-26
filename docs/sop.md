# Standard Operating Procedures (SOP): AI-Driven Development for Arumaldo Cloud

## 1. Introduction

This document outlines the Standard Operating Procedures (SOP) for the AI development team working on the Arumaldo Cloud platform. The development process is 100% AI-driven, utilizing Google Antigravity as the primary Integrated Development Environment (IDE). These procedures are designed to ensure consistency, quality, and efficiency in the development, deployment, and maintenance of the platform.

## 2. Development Environment Setup

1.  **Clone the Repository:** Clone the `ArumaldoCloud` repository from GitHub.
2.  **Install Dependencies:** Run `pnpm install` to install all required dependencies.
3.  **Configure Environment Variables:** Create a `.env` file and populate it with the necessary API keys and secrets for Supabase, Zoho, Cloudflare, and other services. Refer to the `ADD_SECRETS.md` file for a complete list of required variables.
4.  **Launch Google Antigravity:** Open the project in Google Antigravity to begin development.

## 3. Development Workflow

### 3.1. Sprint Planning

-   Sprints are two weeks long.
-   The AI project manager will assign user stories from the backlog to each sprint.
-   Each user story will have a clear set of acceptance criteria.

### 3.2. Feature Development

1.  **Create a New Branch:** For each new feature, create a new branch from `develop` with the naming convention `feature/<user-story-id>-<short-description>`.
2.  **Develop in Isolation:** All development for a feature must be done in its dedicated branch.
3.  **Follow the Tech Stack:** Adhere to the established tech stack: Refine, Next.js, TypeScript, Tailwind CSS, and Supabase.
4.  **Write Unit Tests:** All new code must be accompanied by unit tests, with a minimum of 80% code coverage.
5.  **Update Documentation:** Any changes to the codebase must be reflected in the relevant documentation.

### 3.3. Code Review and Merging

1.  **Create a Pull Request (PR):** Once a feature is complete, create a PR to merge the feature branch into `develop`.
2.  **AI Peer Review:** Another AI agent will review the PR, checking for code quality, adherence to standards, and test coverage.
3.  **Automated Checks:** The PR will trigger a series of automated checks, including linting, testing, and vulnerability scanning.
4.  **Merge to Develop:** Once the PR is approved and all checks have passed, it will be merged into the `develop` branch.

## 4. Deployment Process

### 4.1. Staging Deployment

-   The `develop` branch is automatically deployed to the staging environment on Vercel.
-   The staging environment is an exact replica of the production environment.
-   All new features must be tested and verified in the staging environment before being deployed to production.

### 4.2. Production Deployment

1.  **Create a Release Branch:** When a new release is ready, create a release branch from `develop` with the naming convention `release/v<version-number>`.
2.  **Merge to Main:** Create a PR to merge the release branch into `main`.
3.  **Tag the Release:** Once the PR is merged, create a new tag with the version number.
4.  **Automated Production Deployment:** The `main` branch is automatically deployed to the production environment on Vercel.

### 4.3. Hotfixes

1.  **Create a Hotfix Branch:** For urgent bug fixes, create a hotfix branch from `main` with the naming convention `hotfix/<bug-id>-<short-description>`.
2.  **Fix the Bug:** Implement the bug fix in the hotfix branch.
3.  **Merge to Main and Develop:** Create a PR to merge the hotfix branch into both `main` and `develop` to ensure the fix is incorporated into future releases.

## 5. AI Agent Collaboration

-   **Communication:** All communication between AI agents will be done through GitHub comments and issues.
-   **Task Assignment:** The AI project manager will assign tasks to individual AI agents via GitHub issues.
-   **Knowledge Sharing:** All new learnings and best practices will be documented and shared in the project's knowledge base.
