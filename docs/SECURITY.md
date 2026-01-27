# Security Policy

## Supported Versions

We aim to support security fixes for:

- The latest released version (tagged release)
- The `production` branch (deployed)

Older versions may not receive security updates. If you are unsure whether you are affected, please report the issue privately.

## Reporting a Vulnerability

Please **do not** report security vulnerabilities through public GitHub issues or Discussions.

Instead, use GitHub Security Advisories (private reporting):

- https://github.com/hamashou74/bookshelf/security/advisories/new

When submitting a report, include:

- A clear description of the vulnerability and impact
- Steps to reproduce (proof-of-concept if safe)
- Affected components (Frontend/Backend/API/DB/CI/CD)
- Any known mitigations or suggested fixes
- Whether the issue is actively exploited (if you have evidence)

### What to expect

We will make a best effort to:

1. Acknowledge receipt of your report
2. Triage severity and confirm reproducibility
3. Work on a fix and coordinate a release
4. Credit reporters where appropriate (unless you prefer to remain anonymous)

## Coordinated Disclosure

Please keep vulnerability details private until a fix is released and maintainers have provided guidance on disclosure timing.

## Security Best Practices for Contributors

- Never commit secrets (tokens, credentials, private keys).
- Scrub sensitive information from logs/screenshots.
- Keep dependencies up to date and prefer minimal privilege in configuration.
- For Django/DRF: validate and authorize on the server side; avoid leaking debug details in production.
- For Next.js: do not expose server-only environment variables to the client.

Thank you for helping keep Bookshelf and its users safe.
