# User Stories and Acceptance Criteria: Arumaldo Cloud

## 1. Introduction

This document contains the user stories for the Arumaldo Cloud platform, organized by feature area. Each user story includes a description, acceptance criteria, and priority.

## 2. User Authentication

### US-001: User Registration

**As a** new user, **I want to** create an account, **so that** I can access the Arumaldo Cloud platform.

| Acceptance Criteria |
| :--- |
| User can register with email and password. |
| User receives a confirmation email after registration. |
| User cannot register with an email that is already in use. |
| User is redirected to the dashboard after successful registration. |

**Priority:** High

### US-002: User Login

**As a** registered user, **I want to** log in to my account, **so that** I can access my dashboard.

| Acceptance Criteria |
| :--- |
| User can log in with email and password. |
| User can enable two-factor authentication (2FA). |
| User is redirected to the dashboard after successful login. |
| User sees an error message if login credentials are incorrect. |

**Priority:** High

## 3. Website Creation

### US-003: Create Website Preview

**As a** customer, **I want to** answer questions about my business and see a preview of my website, **so that** I can decide if I want to proceed.

| Acceptance Criteria |
| :--- |
| Customer is presented with a series of questions about their business. |
| AI generates a visual preview of the website based on the answers. |
| Customer can request unlimited revisions to the preview. |
| No resources are consumed until the customer approves and pays. |

**Priority:** High

### US-004: Approve and Pay for Website

**As a** customer, **I want to** approve my website preview and pay for a subscription, **so that** my website can be created.

| Acceptance Criteria |
| :--- |
| Customer can select a subscription plan (Starter, Professional, Business, Enterprise). |
| Customer can enter payment information (credit card or ACH for annual). |
| Payment is processed via Authorize.net. |
| Subscription is created in Zoho Billing. |
| Website creation begins only after successful payment. |

**Priority:** High

### US-005: Manage Website

**As a** customer, **I want to** manage my website from the dashboard, **so that** I can make changes and view its status.

| Acceptance Criteria |
| :--- |
| Customer can view the status of their website (pending, active, suspended). |
| Customer can access the WordPress admin panel. |
| Customer can view security scan results. |
| Customer can view compliance documents. |

**Priority:** High

## 4. Security

### US-006: View Security Dashboard

**As a** customer, **I want to** view the security status of my website, **so that** I know it is protected.

| Acceptance Criteria |
| :--- |
| Dashboard displays a security score (0-100). |
| Dashboard shows the status of SSL, WAF, and malware scanning. |
| Dashboard displays recent security alerts. |
| Customer can initiate a manual security scan. |

**Priority:** Medium

### US-007: Restore from Backup

**As a** customer, **I want to** restore my website from a backup, **so that** I can recover from an issue.

| Acceptance Criteria |
| :--- |
| Customer can view a list of available backups. |
| Customer can select a backup and initiate a restore. |
| Restore completes within 15 minutes. |
| Customer is notified when the restore is complete. |

**Priority:** Medium

## 5. Compliance

### US-008: Generate Privacy Policy

**As a** customer, **I want to** generate a privacy policy for my website, **so that** I am compliant with data protection regulations.

| Acceptance Criteria |
| :--- |
| Customer can select their jurisdiction (e.g., EU, US). |
| AI generates a privacy policy based on the jurisdiction. |
| Customer can review and edit the generated policy. |
| Policy is automatically published to the website. |

**Priority:** Medium

## 6. Support

### US-009: Get AI Support

**As a** customer, **I want to** get help from an AI support agent, **so that** I can resolve my issues quickly.

| Acceptance Criteria |
| :--- |
| Customer can access a chat interface to talk to the AI agent. |
| AI agent can answer common questions and troubleshoot issues. |
| If the AI cannot resolve the issue, it creates a ticket in Zoho Desk. |
| Customer is notified when a human agent responds to their ticket. |

**Priority:** High

## 7. Billing

### US-010: View Invoices

**As a** customer, **I want to** view my invoices, **so that** I can track my payments.

| Acceptance Criteria |
| :--- |
| Customer can view a list of all invoices. |
| Customer can download invoices as PDF. |
| Invoices are retrieved from Zoho Books. |

**Priority:** Medium

### US-011: Manage Subscription

**As a** customer, **I want to** manage my subscription, **so that** I can upgrade, downgrade, or cancel.

| Acceptance Criteria |
| :--- |
| Customer can view their current subscription plan. |
| Customer can upgrade or downgrade their plan. |
| Customer can cancel their subscription. |
| Changes are reflected in Zoho Billing. |

**Priority:** High
