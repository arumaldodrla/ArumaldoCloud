# Deployment Guide: Arumaldo Cloud

## 1. Introduction

This document provides a step-by-step guide for deploying the Arumaldo Cloud platform. The deployment process is fully automated and leverages Vercel for the frontend and Supabase for the backend.

## 2. Prerequisites

- A Vercel account
- A Supabase account
- A GitHub account
- The `ArumaldoCloud` repository cloned to your local machine

## 3. Environment Configuration

1.  **Supabase:**
    -   Create a new project in Supabase.
    -   Navigate to the "SQL Editor" and run the scripts from `database_schema.md` to create the database schema.
    -   In your project settings, retrieve the following:
        -   Project URL
        -   `anon` key
        -   `service_role` key
        -   JWT Secret

2.  **Vercel:**
    -   Create a new project in Vercel and connect it to your `ArumaldoCloud` GitHub repository.
    -   In the project settings, add the following environment variables:

| Variable | Description |
| :--- | :--- |
| `NEXT_PUBLIC_SUPABASE_URL` | Your Supabase project URL. |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Your Supabase `anon` key. |
| `SUPABASE_SERVICE_ROLE_KEY` | Your Supabase `service_role` key. |
| `SUPABASE_JWT_SECRET` | Your Supabase JWT Secret. |
| `ZOHO_CLIENT_ID` | Your Zoho API client ID. |
| `ZOHO_CLIENT_SECRET` | Your Zoho API client secret. |
| `AUTHORIZE_NET_API_LOGIN_ID` | Your Authorize.net API login ID. |
| `AUTHORIZE_NET_TRANSACTION_KEY` | Your Authorize.net transaction key. |
| `CLOUDFLARE_API_TOKEN` | Your Cloudflare API token. |
| `BREVO_API_KEY` | Your Brevo API key. |
| `PRESSABLE_API_KEY` | Your Pressable API key. |
| `OPENAI_API_KEY` | Your OpenAI API key. |

## 4. Deployment

### 4.1. Staging

-   Any push to the `develop` branch will automatically trigger a deployment to the staging environment on Vercel.
-   The staging URL will be in the format `https://arumaldo-cloud-staging.vercel.app`.

### 4.2. Production

-   Any push to the `main` branch will automatically trigger a deployment to the production environment on Vercel.
-   The production URL will be your custom domain, which you can configure in the Vercel project settings.

## 5. Post-Deployment Steps

1.  **Configure DNS:** Point your custom domain to the Vercel deployment.
2.  **Set up Webhooks:** Configure webhooks in Zoho and other services to send notifications to your Supabase Edge Functions.
3.  **Run End-to-End Tests:** Perform a full suite of end-to-end tests to ensure that all integrations are working correctly.
