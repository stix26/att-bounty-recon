# AT&T Bug Bounty Recon — 2026-07-05

**HackerOne:** AT&T  
**Scope:** att.com  
**Methodology:** Full recon pipeline (subfinder → live probing → CORS → exposed files → nuclei → ffuf)

## Summary

| Step | Status | Findings |
|------|--------|----------|
| Subdomain Enumeration | ✅ | 34,569 subdomains found |
| Live Probing | ✅ | 8 key subdomains checked |
| CORS Testing | ✅ | No misconfigurations detected |
| Exposed Files | ✅ | `/api` and `/backup` return 200 |
| Nuclei Scan | ✅ | Azure AD tenant info |
| FFUF Fuzzing | ✅ | Common paths scanned |

## CORS Results
All tested endpoints (att.com, www.att.com, my.att.com, api.att.com) — No CORS headers.

## Key Subdomains Live
- www.att.com (200)
- my.att.com (403)
- api.att.com (404)

## Notable
- **34,569 subdomains** discovered — very large attack surface
- `/api` and `/backup` paths return HTTP 200 — investigate further

## Nuclei
- **Azure Domain Tenant:** att.com → Azure AD (tenant: e741d71c-c6b6-47b0-803c-0f3b32b07556)
