# Environment Variables Reference: Arumaldo Cloud

## 1. Introduction

This document provides a comprehensive reference for all environment variables required by the Arumaldo Cloud platform. These variables must be configured in your local `.env` file for development and in the Vercel project settings for deployment.

## 2. Supabase

| Variable | Description | Required |
| :--- | :--- | :--- |
| `NEXT_PUBLIC_SUPABASE_URL` | The URL of your Supabase project. | Yes |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | The anonymous (public) key for your Supabase project. | Yes |
| `SUPABASE_SERVICE_ROLE_KEY` | The service role key for your Supabase project. Used for server-side operations. | Yes |
| `SUPABASE_JWT_SECRET` | The JWT secret for your Supabase project. Used for verifying tokens. | Yes |

## 3. Zoho

| Variable | Description | Required |
| :--- | :--- | :--- |
| `ZOHO_CLIENT_ID` | The client ID for your Zoho API application. | Yes |
| `ZOHO_CLIENT_SECRET` | The client secret for your Zoho API application. | Yes |
| `ZOHO_REFRESH_TOKEN` | The refresh token for your Zoho API application. | Yes |
| `ZOHO_ORGANIZATION_ID` | The organization ID for your Zoho account. | Yes |

## 4. Payment Processing

| Variable | Description | Required |
| :--- | :--- | :--- |
| `AUTHORIZE_NET_API_LOGIN_ID` | Your Authorize.net API login ID. | Yes |
| `AUTHORIZE_NET_TRANSACTION_KEY` | Your Authorize.net transaction key. | Yes |
| `AUTHORIZE_NET_ENVIRONMENT` | The Authorize.net environment (`sandbox` or `production`). | Yes |

## 5. Cloudflare

| Variable | Description | Required |
| :--- | :--- | :--- |
| `CLOUDFLARE_API_TOKEN` | Your Cloudflare API token with permissions for DNS and WAF. | Yes |
| `CLOUDFLARE_ZONE_ID` | The zone ID for your Cloudflare account. | Yes |

## 6. Pressable

| Variable | Description | Required |
| :--- | :--- | :--- |
| `PRESSABLE_API_KEY` | Your Pressable API key. | Yes |
| `PRESSABLE_COLLABORATOR_ID` | Your Pressable collaborator ID. | Yes |

## 7. Brevo

| Variable | Description | Required |
| :--- | :--- | :--- |
| `BREVO_API_KEY` | Your Brevo API key. | Yes |

## 8. OpenAI

| Variable | Description | Required |
| :--- | :--- | :--- |
| `OPENAI_API_KEY` | Your OpenAI API key. | Yes |

## 9. Application

| Variable | Description | Required |
| :--- | :--- | :--- |
| `NEXT_PUBLIC_APP_URL` | The public URL of the application (e.g., `https://arumaldocloud.com`). | Yes |
| `ENCRYPTION_KEY` | A 32-byte key used for encrypting sensitive data. | Yes |

## 10. Example `.env` File

```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
SUPABASE_JWT_SECRET=your-jwt-secret

# Zoho
ZOHO_CLIENT_ID=your-zoho-client-id
ZOHO_CLIENT_SECRET=your-zoho-client-secret
ZOHO_REFRESH_TOKEN=your-zoho-refresh-token
ZOHO_ORGANIZATION_ID=your-zoho-organization-id

# Authorize.net
AUTHORIZE_NET_API_LOGIN_ID=your-api-login-id
AUTHORIZE_NET_TRANSACTION_KEY=your-transaction-key
AUTHORIZE_NET_ENVIRONMENT=sandbox

# Cloudflare
CLOUDFLARE_API_TOKEN=your-cloudflare-api-token
CLOUDFLARE_ZONE_ID=your-cloudflare-zone-id

# Pressable
PRESSABLE_API_KEY=your-pressable-api-key
PRESSABLE_COLLABORATOR_ID=your-pressable-collaborator-id

# Brevo
BREVO_API_KEY=your-brevo-api-key

# OpenAI
OPENAI_API_KEY=your-openai-api-key

# Application
NEXT_PUBLIC_APP_URL=http://localhost:3000
ENCRYPTION_KEY=your-32-byte-encryption-key
```
