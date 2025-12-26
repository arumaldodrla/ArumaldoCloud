# Product Requirements Document (PRD): Arumaldo Cloud

## 1. Introduction

Arumaldo Cloud is a unified, AI-powered, security-first platform that provides Website-as-a-Service (WaaS) with integrated DNS management, security, and compliance. It is designed to be developed, maintained, and operated primarily by AI agents, leveraging Google Antigravity as the IDE. This document outlines the product requirements for Arumaldo Cloud, which merges the capabilities of ArumaldoWaaS and Safe-Orbit into a single, cohesive offering.

## 2. Vision

> "The most secure websites in the world, created in minutes, compliant everywhere."

Arumaldo Cloud will be the go-to platform for businesses that want a secure, compliant, and high-performance online presence without the technical overhead. It will be an AI-first platform, with minimal human interaction in the customer lifecycle.

## 3. Target Audience

- **Small to Medium-sized Businesses (SMBs):** Businesses that need a professional website but lack the technical expertise to build and maintain it themselves.
- **Agencies:** Web development and marketing agencies that want to offer website creation and management services to their clients.
- **eCommerce Businesses:** Online stores that require a secure and compliant platform with full WooCommerce support.

## 4. Key Features

### 4.1. AI-Powered Website Builder

- **AI-driven site creation:** Users answer a series of questions about their business, and the AI generates a complete WordPress website, including content, images, and layout.
- **Preview-first workflow:** A visual preview of the website is generated for customer approval before any resources are provisioned.
- **Unlimited revisions:** Customers can request unlimited revisions to the preview before approving and paying.

### 4.2. Security-First Architecture

- **Multi-layered security:** A comprehensive security model that includes edge security (Cloudflare), transport security (SSL/TLS), application security (WAF, malware scanning), data security (encryption), and access security (2FA).
- **Proactive threat prevention:** AI-powered threat intelligence and automated incident response to protect against known and unknown threats.
- **Compliance-as-a-Service:** Automated generation of legal documents (Privacy Policy, Terms of Service), cookie consent management, and continuous compliance monitoring for GDPR, CCPA, and other regulations.

### 4.3. Integrated Platform Services

- **DNS Management:** A centralized DNS management interface with templates, guardrails, and global propagation tracking.
- **Email Authentication:** Guided setup and monitoring of SPF, DKIM, and DMARC to ensure email deliverability and prevent spoofing.
- **Business Email:** Integration with Google Workspace and Microsoft 365 for professional email accounts.
- **Email Marketing:** Individual Brevo accounts for each customer, with full campaign management capabilities.

### 4.4. Full WooCommerce and Plugin Ecosystem

- **Complete eCommerce support:** Full compatibility with WooCommerce and its ecosystem of plugins for payments, bookings, subscriptions, and more.
- **Plugin security framework:** All plugins are scanned for vulnerabilities, monitored for updates, and tested for compatibility.

### 4.5. Fully Automated Self-Service Lifecycle

- **Automated Onboarding:** A fully automated, wizard-driven process for customer sign-up, website creation, and service selection.
- **Automated Service Provisioning:** All services, including WordPress sites, SSL certificates, and Cloudflare features, are provisioned automatically upon payment.
- **Self-Service Upsells:** Customers can browse and purchase additional services and bundles directly from their dashboard, with automated provisioning.
- **AI-powered support:** An AI support agent will handle all first-line support inquiries, with seamless escalation to a human agent via Zoho Desk when necessary.
- **Automated billing and subscription management:** Integration with Zoho Billing and Zoho Books for automated invoicing and subscription management.

## 5. Tech Stack

- **Frontend:** Refine + Next.js + TypeScript + Tailwind CSS (using Metronic admin template)
- **Backend:** Supabase (PostgreSQL, Auth, Edge Functions)
- **Deployment:** Vercel
- **WordPress Hosting:** Pressable
- **Security:** Cloudflare
- **AI:** Google Antigravity, OpenAI API
- **Business Operations:** Zoho One (CRM, Billing, Books, Desk, Sign, Mail)
- **Payment Processing:** Authorize.net (via Zoho integration)

## 6. Upsellable Services

Arumaldo Cloud will offer a range of upsellable services to generate additional revenue and provide enhanced value to customers. These services will be available for purchase through the self-service dashboard.

- **Premium SSL Certificates:** A range of SSL certificates, including Wildcard, OV, and EV, will be available for purchase.
- **Advanced Security Services:** Including advanced WAF rules, penetration testing, and premium vulnerability scanning.
- **Performance Enhancements:** Including premium CDN, advanced image optimization, and Core Web Vitals monitoring.
- **Compliance Add-ons:** Including advanced cookie consent management and accessibility compliance.

## 7. Non-Functional Requirements

- **Security:** The platform must be compliant with the latest data security and privacy regulations, including ISO 27001, SOC 2, GDPR, and CCPA.
- **Scalability:** The architecture must be able to scale to support thousands of customer websites.
- **Performance:** Websites created on the platform must be fast and responsive, with a target page load time of under 1.5 seconds.
- **Reliability:** The platform must have an uptime of 99.99%.
