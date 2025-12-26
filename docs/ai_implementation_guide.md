# AI Implementation Guide: Google Antigravity for Arumaldo Cloud

## 1. Introduction

This guide provides detailed instructions for AI agents using Google Antigravity to develop the Arumaldo Cloud platform. Google Antigravity is an AI-powered IDE that supports multiple AI models, including Anthropic's Claude Sonnet 4.5 and Opus 4.5, as well as open-source variants of OpenAI models. This document outlines best practices for leveraging these capabilities to build a robust, secure, and compliant platform.

## 2. Understanding the Project

Before writing any code, AI agents must thoroughly understand the project requirements and architecture.

| Document | Purpose |
| :--- | :--- |
| [PRD](./prd.md) | Defines the product vision, features, and requirements. |
| [System Architecture](./system_architecture.md) | Describes the technical architecture and component interactions. |
| [Database Schema](./database_schema.md) | Defines the database tables and relationships. |
| [Zoho Integration](./zoho_integration.md) | Details the integration with Zoho One services. |
| [Compliance & Security](./compliance_security.md) | Outlines the security and compliance requirements. |

## 3. Development Methodology

### 3.1 Sandboxing

The "sandboxing" methodology involves developing and testing individual components in isolation before integrating them into the main codebase. This approach reduces the risk of introducing bugs and makes it easier to identify and fix issues.

1.  **Create a Sandbox:** For each new feature, create a new branch and a dedicated test environment.
2.  **Develop in Isolation:** Implement the feature in the sandbox, writing unit tests as you go.
3.  **Test Thoroughly:** Run all unit and integration tests to ensure the feature works as expected.
4.  **Integrate:** Once the feature is complete and tested, merge it into the `develop` branch.

### 3.2 Prompting Strategy

Effective prompting is key to getting the best results from AI models. Follow these guidelines:

| Principle | Description |
| :--- | :--- |
| **Be Specific** | Clearly define the task, including inputs, outputs, and acceptance criteria. |
| **Provide Context** | Include relevant code snippets, documentation links, and error messages. |
| **Break Down Complex Tasks** | Divide large tasks into smaller, manageable subtasks. |
| **Iterate** | Refine your prompts based on the AI's output. |

### 3.3 Example Prompts

**Creating a Supabase Edge Function:**

> "Create a Supabase Edge Function in TypeScript called `create-zoho-contact`. This function should accept a JSON payload with `email`, `firstName`, and `lastName` fields. It should call the Zoho CRM API to create a new contact with these details. The function should return a JSON response with the new contact's ID. Handle potential errors, such as invalid input or API failures, and return appropriate error messages. Use the `ZOHO_CLIENT_ID` and `ZOHO_CLIENT_SECRET` environment variables for authentication."

**Creating a React Component:**

> "Create a React component called `SubscriptionCard` using TypeScript and Tailwind CSS. The component should display a subscription plan, including its name, price, and a list of features. It should accept the following props: `name` (string), `price` (number), `features` (array of strings), and `onSelect` (function). Use the Metronic design system for styling."

## 4. Code Quality Standards

### 4.1 TypeScript

All code must be written in TypeScript with strict type checking enabled. This ensures type safety and improves code maintainability.

### 4.2 Linting and Formatting

All code must adhere to the ESLint rules defined in the project. Code will be automatically formatted using Prettier on commit.

### 4.3 Testing

All new code must be accompanied by unit tests, with a minimum of 80% code coverage. Use Jest and React Testing Library for frontend tests and Vitest for backend tests.

## 5. Security Considerations

AI agents must be vigilant about security when writing code.

| Consideration | Implementation |
| :--- | :--- |
| **Input Validation** | Always validate user input to prevent injection attacks. |
| **Output Encoding** | Encode output to prevent XSS attacks. |
| **Secrets Management** | Never hardcode secrets in the codebase. Use environment variables. |
| **Least Privilege** | Grant only the minimum necessary permissions. |

## 6. Collaboration

AI agents will collaborate through GitHub issues and pull requests. All code changes must be reviewed by another AI agent before being merged. Communication should be clear, concise, and focused on the task at hand.
