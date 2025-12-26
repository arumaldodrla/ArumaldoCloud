# Database Schema: Arumaldo Cloud

## 1. Introduction

This document defines the PostgreSQL database schema for the Arumaldo Cloud platform, hosted on Supabase. The schema is designed to support a multi-tenant architecture, with row-level security (RLS) policies to ensure data isolation between customers.

## 2. Tables

### `users`

Stores user account information.

| Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- |
| `id` | `uuid` | Primary Key, Default: `uuid_generate_v4()` | Unique identifier for the user. |
| `email` | `text` | Not Null, Unique | User's email address. |
| `created_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the user was created. |
| `updated_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the user was last updated. |
| `zoho_contact_id` | `text` | | The user's contact ID in Zoho CRM. |

### `websites`

Stores information about customer websites.

| Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- |
| `id` | `uuid` | Primary Key, Default: `uuid_generate_v4()` | Unique identifier for the website. |
| `user_id` | `uuid` | Not Null, Foreign Key to `users(id)` | The user who owns the website. |
| `name` | `text` | Not Null | The name of the website. |
| `domain` | `text` | Not Null, Unique | The primary domain of the website. |
| `pressable_site_id` | `text` | | The website's ID in Pressable. |
| `status` | `text` | Not Null, Default: `'pending'` | The status of the website (e.g., `pending`, `active`, `suspended`). |
| `created_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the website was created. |
| `updated_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the website was last updated. |

### `domains`

Stores information about customer domains.

| Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- |
| `id` | `uuid` | Primary Key, Default: `uuid_generate_v4()` | Unique identifier for the domain. |
| `website_id` | `uuid` | Not Null, Foreign Key to `websites(id)` | The website the domain is associated with. |
| `domain_name` | `text` | Not Null, Unique | The domain name. |
| `provider` | `text` | | The DNS provider (e.g., `Cloudflare`). |
| `status` | `text` | Not Null, Default: `'unverified'` | The status of the domain (e.g., `unverified`, `verified`). |
| `created_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the domain was created. |
| `updated_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the domain was last updated. |

### `security_scans`

Stores the results of security scans.

| Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- |
| `id` | `uuid` | Primary Key, Default: `uuid_generate_v4()` | Unique identifier for the scan. |
| `website_id` | `uuid` | Not Null, Foreign Key to `websites(id)` | The website that was scanned. |
| `scan_type` | `text` | Not Null | The type of scan (e.g., `malware`, `vulnerability`). |
| `results` | `jsonb` | | The results of the scan. |
| `status` | `text` | Not Null, Default: `'completed'` | The status of the scan. |
| `created_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the scan was created. |

### `compliance_documents`

Stores generated compliance documents.

| Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- |
| `id` | `uuid` | Primary Key, Default: `uuid_generate_v4()` | Unique identifier for the document. |
| `website_id` | `uuid` | Not Null, Foreign Key to `websites(id)` | The website the document is for. |
| `document_type` | `text` | Not Null | The type of document (e.g., `privacy_policy`, `terms_of_service`). |
| `content` | `text` | | The content of the document. |
| `version` | `integer` | Not Null, Default: `1` | The version of the document. |
| `created_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the document was created. |
| `updated_at` | `timestamp with time zone` | Not Null, Default: `now()` | Timestamp of when the document was last updated. |

## 3. Row-Level Security (RLS) Policies

RLS policies are enabled on all tables to ensure that users can only access their own data.

### Example RLS Policy for `websites` table:

```sql
CREATE POLICY "Users can only see their own websites." ON websites
FOR SELECT
USING (auth.uid() = user_id);
```

Similar policies will be applied to all other tables to enforce data isolation.
