# Cloudflare Integration Guide: Partner Program & Reselling

## 1. Introduction

This document outlines the strategy for integrating with Cloudflare as a partner to resell their services. Arumaldo Cloud will leverage the Cloudflare Self-Serve Agency Program to offer a wide range of security and performance features to its customers. This integration is key to providing a comprehensive, self-service platform with significant upsell potential.

## 2. Cloudflare Partner Program

### 2.1 Recommended Program: Self-Serve Agency Program

- **Benefits:**
    - Multi-tenant dashboard for managing all client accounts.
    - Centralized billing with a single invoice for all clients.
    - Discounted pricing on all self-serve products.
    - No revenue commitments or fees during the beta period.

- **How to Apply:**
    1. Create a new Cloudflare account (separate from any existing accounts).
    2. Apply at [https://www.cloudflare.com/cloudflare-partners-self-serve-program-open-beta/](https://www.cloudflare.com/cloudflare-partners-self-serve-program-open-beta/).
    3. Add a credit card to the new account.
    4. Wait for approval (2-4 weeks).

### 2.2 Tenant API for Automation

Once approved as a partner, Arumaldo Cloud will use the Cloudflare Tenant API to automate the provisioning and management of customer accounts and services. This is crucial for delivering a seamless, self-service experience.

## 3. Resellable Cloudflare Services

Arumaldo Cloud will resell the following Cloudflare services, with a markup to generate revenue:

| Service | Your Cost (Est. with discount) | Suggested Retail Price | Margin Potential |
| :--- | :--- | :--- | :--- |
| **Pro Plan** | ~$20 / month | $35 - $50 / month | 75-150% |
| **Business Plan** | ~$160 / month | $250 - $350 / month | 55-120% |
| **Argo Smart Routing** | ~$4 / month + usage | $15 - $25 / month | 275%+ |
| **Load Balancing** | ~$4 / month + usage | $20 - $40 / month | 400%+ |
| **Advanced Certificate Manager** | ~$8 / month | $20 - $30 / month | 150-275% |

## 4. Cloudflare for SaaS (Custom Hostnames)

For managing customer domains that are not hosted on Pressable, Arumaldo Cloud will use the Cloudflare for SaaS offering.

- **Pricing:**
    - 100 hostnames included for free.
    - $0.10 per additional hostname per month.

- **Revenue Model:**
    - Charge customers $1 - $5 per month per custom hostname.
    - This creates a significant margin on a high-volume service.

## 5. Integration Architecture

1. **Customer Onboarding:** When a customer signs up for a plan that includes Cloudflare services, a new child account is created under the Arumaldo Cloud agency account via the Tenant API.
2. **Service Provisioning:** The selected Cloudflare services (e.g., Pro plan, Argo) are provisioned for the customer's account using the Tenant API.
3. **Billing:** The customer is billed through Zoho Billing for the selected services, including the markup.
4. **Management:** The customer can manage their Cloudflare settings through a simplified interface in the Arumaldo Cloud portal, which makes calls to the Cloudflare API on their behalf.

## 6. Development Considerations

- **API Wrapper:** Create a dedicated API wrapper for the Cloudflare Tenant API to simplify interactions and handle authentication.
- **Feature Gating:** Implement feature gating to control which Cloudflare features are available to customers based on their subscription plan.
- **Usage-Based Billing:** For services with usage-based pricing (e.g., Argo), integrate with Cloudflare's billing API to track usage and bill customers accordingly.
