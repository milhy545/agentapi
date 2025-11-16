# Security Policy

## Supported Versions

We release patches for security vulnerabilities in the following versions:

| Version | Supported          |
| ------- | ------------------ |
| 0.11.x  | :white_check_mark: |
| 0.10.x  | :white_check_mark: |
| < 0.10  | :x:                |

## Reporting a Vulnerability

We take the security of AgentAPI seriously. If you believe you have found a security vulnerability, please report it to us as described below.

### How to Report

**Please do not report security vulnerabilities through public GitHub issues.**

Instead, please report them via one of the following methods:

1. **GitHub Security Advisories** (Preferred)
   - Go to the [Security tab](https://github.com/coder/agentapi/security/advisories) of this repository
   - Click "Report a vulnerability"
   - Fill out the form with details about the vulnerability

2. **Email**
   - Send an email to the maintainers listed in [MAINTAINERS.md](MAINTAINERS.md)
   - Include the word "SECURITY" in the subject line

### What to Include

Please include the following information in your report:

- Type of vulnerability (e.g., buffer overflow, SQL injection, cross-site scripting, etc.)
- Full paths of source file(s) related to the manifestation of the vulnerability
- The location of the affected source code (tag/branch/commit or direct URL)
- Any special configuration required to reproduce the issue
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the issue, including how an attacker might exploit it

### What to Expect

- You should receive an acknowledgment within 48 hours
- We will investigate and validate the vulnerability
- We will work on a fix and coordinate disclosure timing with you
- Once the vulnerability is fixed, we will:
  - Release a security advisory
  - Credit you for the discovery (unless you prefer to remain anonymous)
  - Release a patched version

### Security Update Process

When a security vulnerability is confirmed:

1. A fix will be developed in a private repository
2. A security advisory will be drafted
3. A new version will be released with the fix
4. The security advisory will be published
5. Users will be notified through GitHub releases and the advisory

## Security Best Practices

When using AgentAPI:

1. **Keep AgentAPI Updated**: Always use the latest version to benefit from security patches
2. **Restrict Access**: Use the `--allowed-hosts` and `--allowed-origins` flags to limit access
3. **Network Security**: Run AgentAPI behind a firewall or reverse proxy when exposing it to networks
4. **Monitor Logs**: Regularly review logs for suspicious activity
5. **File Uploads**: Be aware that the file upload feature allows uploading files up to 10MB - ensure proper access controls

## Known Security Considerations

- AgentAPI provides an HTTP API to control CLI agents. Ensure proper network isolation and access controls.
- The server accepts file uploads up to 10MB. Consider the security implications in your deployment.
- When using `--allowed-hosts '*'` or `--allowed-origins '*'`, you're allowing access from any host/origin. Use with caution.

## Security-Related Configuration

- `--allowed-hosts`: Controls which hosts can access the API (default: localhost, 127.0.0.1, ::1)
- `--allowed-origins`: Controls CORS origins (default: http://localhost:3284, http://localhost:3000, http://localhost:3001)
- File upload size limit: 10MB (hardcoded)

For more information, see the [README.md](README.md).
