# System Architecture: Arumaldo Cloud

## 1. Introduction

This document provides a comprehensive overview of the system architecture for the Arumaldo Cloud platform. The architecture is designed to be serverless, scalable, and secure, leveraging best-in-class cloud services to minimize operational overhead and maximize reliability.

## 2. High-Level Architecture

The platform is built on a modern, serverless architecture that separates concerns into distinct layers.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         ARUMALDO CLOUD PLATFORM                             │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │                        USER INTERFACE LAYER                           │ │
│  │   Customer Portal  │  Admin Dashboard  │  AI Support Chat             │ │
│  │   (Refine + Next.js + Metronic)                                       │ │
│  └───────────────────────────────────────────────────────────────────────┘ │
│                                    ↓                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │                        APPLICATION LAYER                              │ │
│  │   WaaS Engine  │  SafeOrbit Security  │  Compliance Engine            │ │
│  │   (Supabase Edge Functions)                                           │ │
│  └───────────────────────────────────────────────────────────────────────┘ │
│                                    ↓                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │                          DATA LAYER                                   │ │
│  │   PostgreSQL (Supabase)  │  Supabase Auth  │  Supabase Storage        │ │
│  └───────────────────────────────────────────────────────────────────────┘ │
│                                    ↓                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │                       INTEGRATION LAYER                               │ │
│  │   Zoho One  │  Cloudflare  │  Pressable  │  Brevo  │  Authorize.net   │ │
│  └───────────────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 3. Component Details

### 3.1 User Interface Layer

The frontend is built with Refine, a React-based framework for building data-intensive applications, combined with Next.js for server-side rendering and Tailwind CSS for styling. The Metronic admin template provides a comprehensive set of UI components.

| Component | Technology | Deployment |
| :--- | :--- | :--- |
| Customer Portal | Refine + Next.js | Vercel |
| Admin Dashboard | Refine + Next.js | Vercel |
| AI Support Chat | Custom React Component | Vercel |

### 3.2 Application Layer

The business logic is implemented as Supabase Edge Functions, written in TypeScript. These functions handle all interactions with external services and orchestrate the platform's core workflows.

| Function | Purpose |
| :--- | :--- |
| `create-website` | Provisions a new WordPress site on Pressable. |
| `sync-zoho-crm` | Synchronizes customer data with Zoho CRM. |
| `process-payment` | Handles payment processing via Authorize.net. |
| `run-security-scan` | Triggers a security scan for a website. |
| `generate-compliance-doc` | Generates a compliance document using AI. |

### 3.3 Data Layer

Supabase provides a fully managed PostgreSQL database, along with authentication and file storage services.

| Service | Purpose |
| :--- | :--- |
| PostgreSQL | Stores all application data. |
| Supabase Auth | Manages user authentication and sessions. |
| Supabase Storage | Stores user-uploaded files and assets. |

### 3.4 Integration Layer

The platform integrates with a variety of third-party services to provide a complete solution.

| Service | Purpose |
| :--- | :--- |
| **Zoho One** | CRM, Billing, Support Ticketing, Contracts |
| **Cloudflare** | DNS, CDN, WAF, DDoS Protection |
| **Pressable** | Managed WordPress Hosting |
| **Brevo** | Email Marketing |
| **Authorize.net** | Payment Processing |
| **OpenAI** | AI Content Generation |

## 4. Data Flow

### 4.1 Customer Onboarding Flow

1.  Customer signs up via the Customer Portal.
2.  Supabase Auth creates a new user account.
3.  An Edge Function creates a corresponding contact in Zoho CRM.
4.  Customer answers questions about their business.
5.  An Edge Function uses OpenAI to generate a website preview.
6.  Customer approves the preview and selects a plan.
7.  An Edge Function processes the payment via Authorize.net.
8.  An Edge Function creates a new subscription in Zoho Billing.
9.  An Edge Function provisions a new WordPress site on Pressable.
10. Customer receives access to their new website.

## 5. Scalability

The serverless architecture ensures that the platform can scale automatically to handle any load. Vercel and Supabase both provide automatic scaling, so there is no need to provision or manage servers.

## 6. Reliability

The platform is designed for high availability, with a target uptime of 99.99%. All critical components are redundant, and automated failover mechanisms are in place to ensure continuous operation.
