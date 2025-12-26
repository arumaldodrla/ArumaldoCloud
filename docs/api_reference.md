# API Reference: Arumaldo Cloud

## 1. Introduction

This document provides a reference for the Arumaldo Cloud API. The API is built on Supabase Edge Functions and provides endpoints for managing websites, domains, security scans, and compliance documents.

## 2. Authentication

All API requests must be authenticated using a Bearer token. The token is obtained by logging in via Supabase Auth.

```
Authorization: Bearer <access_token>
```

## 3. Endpoints

### 3.1 Websites

#### Create Website

Creates a new website for the authenticated user.

| Property | Value |
| :--- | :--- |
| **Method** | `POST` |
| **Endpoint** | `/functions/v1/create-website` |

**Request Body:**

```json
{
  "name": "My Business Website",
  "domain": "mybusiness.com",
  "plan": "professional"
}
```

**Response:**

```json
{
  "id": "uuid",
  "name": "My Business Website",
  "domain": "mybusiness.com",
  "status": "pending",
  "created_at": "2024-12-25T00:00:00Z"
}
```

#### Get Website

Retrieves details for a specific website.

| Property | Value |
| :--- | :--- |
| **Method** | `GET` |
| **Endpoint** | `/functions/v1/get-website?id={website_id}` |

**Response:**

```json
{
  "id": "uuid",
  "name": "My Business Website",
  "domain": "mybusiness.com",
  "status": "active",
  "created_at": "2024-12-25T00:00:00Z",
  "updated_at": "2024-12-25T00:00:00Z"
}
```

### 3.2 Domains

#### Add Domain

Adds a new domain to a website.

| Property | Value |
| :--- | :--- |
| **Method** | `POST` |
| **Endpoint** | `/functions/v1/add-domain` |

**Request Body:**

```json
{
  "website_id": "uuid",
  "domain_name": "www.mybusiness.com"
}
```

**Response:**

```json
{
  "id": "uuid",
  "domain_name": "www.mybusiness.com",
  "status": "unverified",
  "created_at": "2024-12-25T00:00:00Z"
}
```

#### Verify Domain

Verifies ownership of a domain.

| Property | Value |
| :--- | :--- |
| **Method** | `POST` |
| **Endpoint** | `/functions/v1/verify-domain` |

**Request Body:**

```json
{
  "domain_id": "uuid"
}
```

**Response:**

```json
{
  "id": "uuid",
  "domain_name": "www.mybusiness.com",
  "status": "verified",
  "updated_at": "2024-12-25T00:00:00Z"
}
```

### 3.3 Security Scans

#### Run Security Scan

Initiates a security scan for a website.

| Property | Value |
| :--- | :--- |
| **Method** | `POST` |
| **Endpoint** | `/functions/v1/run-security-scan` |

**Request Body:**

```json
{
  "website_id": "uuid",
  "scan_type": "full"
}
```

**Response:**

```json
{
  "id": "uuid",
  "website_id": "uuid",
  "scan_type": "full",
  "status": "in_progress",
  "created_at": "2024-12-25T00:00:00Z"
}
```

#### Get Scan Results

Retrieves the results of a security scan.

| Property | Value |
| :--- | :--- |
| **Method** | `GET` |
| **Endpoint** | `/functions/v1/get-scan-results?id={scan_id}` |

**Response:**

```json
{
  "id": "uuid",
  "website_id": "uuid",
  "scan_type": "full",
  "status": "completed",
  "results": {
    "vulnerabilities": [],
    "score": 95
  },
  "created_at": "2024-12-25T00:00:00Z"
}
```

### 3.4 Compliance Documents

#### Generate Compliance Document

Generates a compliance document for a website.

| Property | Value |
| :--- | :--- |
| **Method** | `POST` |
| **Endpoint** | `/functions/v1/generate-compliance-doc` |

**Request Body:**

```json
{
  "website_id": "uuid",
  "document_type": "privacy_policy",
  "jurisdiction": "EU"
}
```

**Response:**

```json
{
  "id": "uuid",
  "website_id": "uuid",
  "document_type": "privacy_policy",
  "content": "...",
  "version": 1,
  "created_at": "2024-12-25T00:00:00Z"
}
```

## 4. Error Handling

All API errors are returned in a consistent format.

```json
{
  "error": {
    "code": "INVALID_INPUT",
    "message": "The 'domain' field is required."
  }
}
```

| Error Code | Description |
| :--- | :--- |
| `INVALID_INPUT` | The request body is missing required fields or contains invalid data. |
| `UNAUTHORIZED` | The request is not authenticated or the user does not have permission. |
| `NOT_FOUND` | The requested resource was not found. |
| `INTERNAL_ERROR` | An unexpected error occurred on the server. |
