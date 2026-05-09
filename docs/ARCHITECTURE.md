# Architecture

SentinelWeb is split into a FastAPI backend and a React frontend.

## High-level architecture

```text
Browser
  ↓
NGINX
  ↓
React frontend
  ↓ /api
FastAPI backend
  ↓
SQLite / future PostgreSQL
```

## Backend

The backend is responsible for:

- managing monitored sites
- managing groups
- running HTTP checks
- running DNS checks
- running TLS checks
- running security header checks
- storing check results
- exposing API endpoints for the frontend

## Frontend

The frontend provides:

- dashboard overview
- site management
- group management
- scheduler controls
- security posture dashboard
- security check detail views
- credential vault UI

## Security scan model

SentinelWeb separates scan visibility into three concepts:

```text
Black-box scan
  → public unauthenticated view

Gray-box scan
  → authenticated view through an access layer

White-box scan
  → internal/origin view
```

This distinction is important because modern services are often protected by Cloudflare, Akamai, Imperva, F5, or similar edge providers.

A public scanner may only see the access gateway, not the real origin application.

## Credential vault

Sensitive scan credentials are stored in an encrypted local vault.

The vault is designed to support:

- Cloudflare Access service tokens
- future API keys
- future HTTP authentication profiles
- future per-site scan credentials

Secrets are not returned by the API.

## Deployment model

The current deployment model is:

```text
Internet
  ↓
Cloudflare
  ↓
NGINX
  ↓
Frontend static files
  ↓ /api
FastAPI backend via systemd/Uvicorn
  ↓
SQLite database
```

The backend runs as a systemd service. The frontend is built with Vite and served as static files by NGINX.

## Security posture model

SentinelWeb is designed to identify the difference between:

- the public edge response;
- the authenticated application response;
- the internal/origin response.

This allows more accurate interpretation of security findings.

For example, a public black-box scan may only see a Cloudflare Access authentication page. A gray-box scan using a service token can evaluate the protected application behind that access layer.

## Planned architecture improvements

Future improvements include:

- PostgreSQL support;
- Docker deployment;
- role-based access control;
- per-site scan profiles;
- white-box origin checks;
- edge-vs-origin comparison;
- report generation;
- alerting integrations.