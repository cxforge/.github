# AI Assistant Guidelines for CXForge Solutions

**Purpose:** This document provides guidelines for AI assistants (like Cursor, GitHub Copilot, etc.) working on CXForge repositories to ensure security, consistency, and quality.

---

## 🔒 Confidentiality & Security

### NEVER Include in Public Files

AI assistants must NOT include the following in any public repositories, issues, PRs, or documentation:

- **Secrets & Keys:**
  - API keys, tokens, or passwords (even placeholders like `your-secret-here`)
  - Database connection strings with real credentials
  - Private keys, SSH keys, or certificates
  - Webhook secrets or bearer tokens
  - Cloud provider credentials

- **Infrastructure Details:**
  - Internal domain names (use placeholders like `${WEB_DOMAIN}`)
  - Internal IP addresses
  - VPS provider details (unless publicly known)
  - Database hostnames/ports in production
  - Technology stack specifics in public docs (React, Node.js, Go, Docker, etc.)
  - Infrastructure tooling (reverse proxies, monitoring, orchestration)
  - Container registry paths or image names

- **Sensitive Information:**
  - Employee or customer personal information
  - Business strategy or roadmap specifics
  - Revenue or financial data
  - Security vulnerabilities (see [SECURITY.md](./SECURITY.md) for proper reporting)

### Safe Patterns for Documentation

✅ **DO use:**
- Environment variable placeholders: `${WEBHOOK_SECRET}`, `${DB_PASSWORD}`
- Generic examples: `https://your-domain.com`, `your-registry.io/organization/image:tag`
- Reference external docs for setup: "See our deployment guide for configuration"

❌ **DON'T use:**
- Real example values: `WEBHOOK_SECRET=abc123def456`
- Actual domain names in examples
- Production-specific configuration details

---

## 🚦 Actions Requiring Explicit Approval

Before performing these actions, AI assistants MUST ask for explicit user confirmation:

### Repository Management
- Creating new public repositories
- Changing repository visibility (public → private or vice versa)
- Deleting repositories or branches
- Adding new organization members or collaborators
- Modifying repository settings (branch protection, etc.)

### Code & Deployment
- Pushing directly to `main` or `production` branches
- Modifying GitHub Actions workflows that:
  - Handle secrets or tokens
  - Deploy to production environments
  - Modify infrastructure
- Creating or modifying webhook endpoints
- Changing Docker Compose configurations in production

### Security-Critical
- Modifying authentication or authorization code
- Changing CORS policies
- Modifying rate limiting configurations
- Updating SSL/TLS certificate handling

---

## 📁 Protected File Patterns

AI assistants should NOT read or suggest edits to these files unless explicitly asked:

### Environment & Secrets
```
.env
.env.*
.env.local
.env.production
.env.staging
secrets/
credentials/
keys/
*.key
*.pem
```

### Docker & Local Config
```
docker-compose.override.yml
.docker-config/
```

### Sensitive by Name Pattern
Files containing these keywords in their names (case-insensitive):
- `secret`
- `token`
- `password`
- `credential`
- `key` (when referring to private/secret keys)
- `auth` (when containing credentials)

---

## 📝 Documentation Standards

### When Creating Public Documentation

1. **Use Placeholders:**
   ```bash
   # Good
   export WEBHOOK_SECRET=${YOUR_WEBHOOK_SECRET}
   
   # Bad
   export WEBHOOK_SECRET=ghp_abc123xyz789
   ```

2. **Reference External Guides:**
   ```markdown
   For production setup, see our [internal deployment guide](link-to-private-docs).
   ```

3. **Assume Public Visibility:**
   - Treat all public repo content as visible to competitors
   - Don't document internal processes in public repos
   - Don't reveal future product features prematurely
   - **NEVER expose application library versions or stack specifics** (e.g., "React 18.2.1", "Node.js 20.5.0") — this information helps bad actors identify vulnerable dependencies to exploit

### Code Comments
- Never commit TODOs that reference internal systems
- Don't include debugging code with real values
- Remove console.log statements that might leak data

---

## 🏗️ Architecture Decisions

### When Suggesting Changes

1. **Consider the Plan:**
   - All repositories should have documentation in standardized folders:
     - `.specs/` — Application specifications and standards
     - `.agents/` — AI assistant specific instructions
     - `.plans/` — Task instructions and implementation plans
   - Check these folders for architectural guidance before suggesting changes
   - Ensure suggestions align with documented architecture
   - Don't introduce new dependencies without justification
   - Aim to keep these documentation folders up to date

2. **Staging → Production Flow:**
   - Always suggest staging-first approach
   - Include health check considerations
   - Think about rollback procedures

3. **Infrastructure Consistency:**
   - Follow existing patterns
   - Maintain consistency with monitoring/logging approach
   - Use existing naming conventions

---

## 🌍 Multi-Language Considerations

### For Latin American Expansion

When working on user-facing content:
- **Design for translation infrastructure from day one** — applications should support multiple languages by simply adding new translation files/processes
- Consider Portuguese (pt-BR) and Spanish (es) i18n
- Use neutral Spanish for broader Latin America coverage
- Be aware of cultural context in UX copy

### Code & Comments
- **All code comments must be in English** — this is the official development language
- Primary language for all development: English
- User-facing strings should be externalized for translation

---

## ✅ Quality Checklist

Before suggesting any code change:

- [ ] No secrets or credentials exposed
- [ ] No internal domains/IPs in examples
- [ ] Environment variables use placeholder syntax
- [ ] Error messages don't leak sensitive info
- [ ] Logging doesn't include PII or secrets
- [ ] Tests don't use real credentials
- [ ] Documentation uses generic examples

---

## 🆘 When in Doubt

**If you're unsure whether something is sensitive:**

1. Ask the user explicitly
2. Default to treating it as sensitive
3. Suggest the change without the sensitive part
4. Document what the user needs to fill in

**Example:**
```markdown
"To configure this service, you'll need to:
1. Generate a webhook secret: `openssl rand -hex 32`
2. Add it to your environment variables
3. Configure the webhook endpoint in your infrastructure"
```

---

## 📚 Reference Documents

- [Brand Guidelines](./brand/README.md) — CXForge brand standards
- [Security Policy](./SECURITY.md) — Reporting security issues
- [Contributing Guide](./CONTRIBUTING.md) — How to contribute (coming soon)

