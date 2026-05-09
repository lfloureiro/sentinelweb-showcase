
---

### **ROADMAP.md**

```markdown
# SentinelWeb Roadmap

## Completed / in progress

- Site management
- Group management
- HTTP availability checks
- DNS health checks
- TLS certificate checks
- Security header scoring
- Security posture dashboard
- Cloudflare Access detection
- Gray-box scan support
- Encrypted credential vault
- NGINX/systemd deployment workflow

## Next priorities

### 1. Incident history

Track and aggregate failures over time.

Planned:

- incident table
- grouped outages
- per-site availability history
- mean time to recovery
- last failure summary

### 2. Security posture improvements

Planned:

- better distinction between edge, origin, and authenticated scans  

- Cloudflare/Akamai/Imperva detection  

- WAF and access-layer recognition
- origin exposure warnings
- HTTP method checks  

- redirect-chain security analysis

### 3. Reporting

Planned:

- CSV export
- PDF reports
- executive summary view
- per-site remediation checklist

### 4. Alerting

Planned:

- email alerts
- webhook alerts
- Discord/Slack notifications
- per-site alert thresholds
- per-group alert routing

### 5. White-box scans

Planned:

- internal URL support
- custom Host header
- origin-vs-edge comparison
- internal-only check profiles

### 6. Authentication and roles

Planned:

- app-level authentication
- admin/read-only roles
- audit log
- multi-user support

### 7. Deployment maturity

Planned:

- Docker deployment
- PostgreSQL support
- backup/restore workflow
- production hardening guide