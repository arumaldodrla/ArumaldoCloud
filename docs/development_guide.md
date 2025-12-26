# Development Guide: Arumaldo Cloud

## 1. Introduction

This guide provides instructions and best practices for AI agents developing the Arumaldo Cloud platform using Google Antigravity. The goal is to ensure a consistent, high-quality, and efficient development process.

## 2. Getting Started

1.  **Clone the Repository:**
    ```bash
    gh repo clone arumaldodrla/ArumaldoCloud
    ```
2.  **Install Dependencies:**
    ```bash
    cd ArumaldoCloud
    pnpm install
    ```
3.  **Set Up Environment Variables:**
    -   Copy the `.env.example` file to `.env`.
    -   Fill in the required API keys and secrets for all integrated services (Supabase, Zoho, Cloudflare, etc.).

## 3. Tech Stack

-   **Frontend:** Refine + Next.js + TypeScript + Tailwind CSS
-   **UI Components:** Metronic Admin Template (ReUI components)
-   **Backend:** Supabase (PostgreSQL, Auth, Edge Functions)
-   **Deployment:** Vercel

## 4. AI-Driven Development with Google Antigravity

### 4.1. Core Principles

-   **Modularity:** Break down complex problems into smaller, manageable functions and components.
-   **Clarity:** Write clear, concise, and well-documented code.
-   **Autonomy:** AI agents are expected to take ownership of their assigned tasks and see them through to completion.

### 4.2. Prompting Best Practices

-   **Be Specific:** Provide detailed instructions and acceptance criteria in your prompts.
-   **Provide Context:** Include relevant code snippets, error messages, and documentation links.
-   **Iterate:** Start with a high-level prompt and then refine it based on the AI's output.

### 4.3. Example Prompt

> "Create a new Supabase Edge Function in TypeScript that retrieves a customer's subscription status from Zoho Billing. The function should take a `customerId` as input and return the subscription status as a string. Ensure you handle potential errors, such as an invalid `customerId` or an API connection failure. Here is the Zoho Billing API documentation for reference: [link to docs]"

## 5. Coding Standards

-   **Linting:** All code must adhere to the ESLint rules defined in the project.
-   **Formatting:** Code will be automatically formatted using Prettier on commit.
-   **Naming Conventions:**
    -   Components: `PascalCase`
    -   Functions and variables: `camelCase`
    -   Files: `kebab-case`

## 6. Testing

-   **Unit Tests:** Use Jest and React Testing Library to write unit tests for all new components and functions.
-   **Integration Tests:** Write integration tests to ensure that different parts of the application work together as expected.
-   **End-to-End Tests:** Use Cypress to write end-to-end tests that simulate user workflows.

## 7. Debugging

-   **Browser DevTools:** Use the browser's developer tools to inspect the DOM, debug JavaScript, and analyze network requests.
-   **Supabase Logs:** Use the Supabase dashboard to view logs for your database and Edge Functions.
-   **Vercel Logs:** Use the Vercel dashboard to view logs for your frontend application.
