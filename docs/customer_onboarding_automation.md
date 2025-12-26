# Customer Onboarding Automation: Arumaldo Cloud

## 1. Introduction

This document outlines the fully automated, self-service customer onboarding process for the Arumaldo Cloud platform. The entire onboarding flow is designed to be seamless and require no human intervention, from initial sign-up to website deployment.

## 2. Onboarding Flow

The onboarding process is a linear, step-by-step flow that guides the customer through the creation of their account and website.

```mermaid
graph TD
    A[Start: Customer clicks "Sign Up"] --> B{Account Creation};
    B --> C{AI Website Creation Wizard};
    C --> D{Plan Selection};
    D --> E{Payment & Checkout};
    E --> F{Automated Provisioning};
    F --> G[End: Dashboard Access & Welcome];
```

## 3. Step-by-Step Breakdown

### Step 1: Account Creation

1.  **Action:** The customer provides their email address and a password.
2.  **Automation:**
    - A new user account is created in Supabase Auth.
    - A confirmation email is sent to the customer's email address.
    - A new contact is created in Zoho CRM with the tag `status:prospect`.

### Step 2: AI Website Creation Wizard

1.  **Action:** The customer is guided through a wizard that asks a series of questions about their business, including:
    - Business name and industry.
    - Target audience and goals.
    - Desired color scheme and style.
    - Key services or products.
2.  **Automation:**
    - The answers are sent to an OpenAI-powered Edge Function.
    - The AI generates a complete website preview, including content, images, and layout.
    - The customer can request unlimited revisions to the preview.

### Step 3: Plan Selection

1.  **Action:** The customer is presented with the available subscription plans (e.g., Starter, Professional, Business, Enterprise) and any optional upsell services (e.g., premium SSL, advanced security).
2.  **Automation:**
    - The selected plan and services are added to the customer's cart.

### Step 4: Payment & Checkout

1.  **Action:** The customer enters their payment information (credit card or ACH for annual plans).
2.  **Automation:**
    - The payment is processed through Authorize.net.
    - Upon successful payment, a new subscription is created in Zoho Billing.
    - The customer's tag in Zoho CRM is updated to `status:active` and `plan:<plan_name>`.

### Step 5: Automated Provisioning

This step is triggered automatically after successful payment and is the core of the self-service automation.

1.  **WordPress Site Creation:**
    - An Edge Function calls the Pressable API to create a new WordPress site.
2.  **Cloudflare Account Creation:**
    - An Edge Function calls the Cloudflare Tenant API to create a new child account for the customer.
3.  **Cloudflare Service Provisioning:**
    - The selected Cloudflare services (e.g., Pro plan, Argo) are provisioned for the customer's account via the Tenant API.
4.  **SSL Certificate Issuance:**
    - If a premium SSL certificate was purchased, an Edge Function calls the SSL reseller's API to issue and install the certificate.
5.  **DNS Configuration:**
    - The necessary DNS records are created in the customer's Cloudflare account to point their domain to the Pressable site.

### Step 6: Dashboard Access & Welcome

1.  **Action:** The customer is redirected to their Arumaldo Cloud dashboard.
2.  **Automation:**
    - A welcome email is sent to the customer with their login details and a link to their new website.
    - The dashboard displays the status of their website and all provisioned services.

## 4. Technical Implementation Notes

- **State Management:** The entire onboarding flow will be managed by a state machine to ensure that the customer can pause and resume the process at any time.
- **Idempotency:** All API calls for provisioning will be idempotent to prevent duplicate resources from being created in case of errors or retries.
- **Error Handling:** A robust error handling and notification system will be in place to alert the support team of any failures in the automated onboarding process.
