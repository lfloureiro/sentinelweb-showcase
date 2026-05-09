# SentinelWeb

**SentinelWeb** is a professional web monitoring and security posture dashboard designed for HTTP/HTTPS availability monitoring, DNS health checks, TLS visibility, and security header assessment.

The project is currently developed as a private codebase. This public repository acts as a project showcase, roadmap, and collaboration entry point.

## What SentinelWeb does

SentinelWeb helps monitor and assess web-facing services by combining availability checks with security-oriented visibility.

Current and planned capabilities include:

- HTTP/HTTPS availability monitoring
- DNS health checks
- TLS certificate monitoring
- Security header scoring
- Black-box public scans
- Gray-box authenticated scans
- Cloudflare Access-aware detection
- Encrypted credentials vault for protected checks
- Security posture dashboard
- Future incident history and reporting

## Why it exists

Many internal and public-facing services are monitored only for uptime, while important security signals such as TLS quality, DNS health, missing headers, exposed technologies, and access-layer behaviour are ignored.

SentinelWeb aims to combine operational monitoring with blue-team visibility.

## Current status

The project is under active development.

Implemented so far:

- FastAPI backend
- React + TypeScript frontend
- SQLite-backed persistence
- Site and group management
- HTTP checks
- DNS checks
- TLS checks
- Security header checks
- Cloudflare Access detection
- Gray-box checks using service-token authentication
- Encrypted local vault for protected scan credentials
- NGINX deployment support
- systemd deployment support
- Cloudflare-aware publication model

## Scan modes

SentinelWeb distinguishes between different levels of visibility.

### Black-box scan

Tests what an anonymous public user sees from the Internet.

Useful for:

- public exposure checks
- Cloudflare/Akamai/Imperva detection
- unauthenticated surface assessment

### Gray-box scan

Tests a protected application using authorised credentials, such as Cloudflare Access service tokens.

Useful for:

- validating the real application behind an access gateway
- avoiding false positives from login/interstitial pages
- checking headers and posture after authentication

### White-box scan

Planned mode for testing internal/origin services directly from trusted networks.

Useful for:

- checking reverse proxy/origin configuration
- comparing edge vs origin posture
- validating internal-only services

## Technology stack

| Layer | Technology |
|---|---|
| Backend | FastAPI |
| Data model | SQLModel |
| Database | SQLite, future PostgreSQL support |
| Frontend | React |
| Language | TypeScript |
| Build tool | Vite |
| Deployment | NGINX + systemd |
| Security checks | HTTPX-based scanner |
| Credential storage | Encrypted local vault |

## Screenshots

Screenshots will be added as the UI stabilises.

Suggested screenshots:

- dashboard overview
- monitored sites list
- security posture cards
- security detail view
- vault credentials modal
- black-box vs gray-box result comparison

## Repository access

The source code is currently private.

If you are interested in reviewing, testing, contributing, or discussing the project, please contact the maintainer.

## Contact

Open an issue in this showcase repository or contact the maintainer directly through GitHub.

## License

The public showcase content is provided for informational purposes.

The application source code is not publicly licensed at this stage.