# Codexa - Security & Privacy Policy

Last Updated: April 26, 2026

---

## 1. Overview

Codexa is committed to protecting your privacy and security. This document outlines our security practices and privacy policies.

### Core Principles
- **Privacy First** - Your data is yours. We don't sell or share it.
- **Local Storage** - Your code stays on your device by default
- **Encryption** - Data in transit is encrypted with TLS/SSL
- **Transparency** - We're open about what data we collect

---

## 2. Data We Collect

### Required Data
- **Account Information** - Email, name, password (hashed)
- **Usage Analytics** - Features used, session duration
- **Error Logs** - To improve the service

### Optional Data
- **OpenAI API Key** - Stored ONLY in your browser, never on our servers
- **File Content** - Only if you explicitly share or export
- **Payment Information** - Processed by Stripe (we never see full card numbers)

### Data We DON'T Collect
- ❌ Your source code (it stays on your device)
- ❌ Browser cookies (except for authentication)
- ❌ IP addresses for tracking
- ❌ Personal information beyond account setup
- ❌ Third-party data about you

---

## 3. Data Storage & Security

### Local Storage (Client-Side)
```
Your Browser
├── Files (all your code)
├── API Key (encrypted)
├── Settings
└── Chat History
```
**Location**: Only on your device
**Security**: Browser sandboxing + encryption
**Accessible by**: Only you

### Server Storage (Codexa Infrastructure)
```
Codexa Servers
├── Account Information (email, hashed password)
├── Usage Statistics (anonymous)
├── Billing Information (via Stripe)
└── Support Data (if you contact us)
```
**Location**: AWS encrypted servers (US-East-1)
**Security**: Enterprise-grade encryption (AES-256)
**Access**: Only authorized Codexa employees

---

## 4. Encryption Standards

### In Transit (TLS/SSL)
- **Protocol**: TLS 1.3 minimum
- **Certificate**: Let's Encrypt (auto-renewed)
- **Cipher Suites**: 256-bit encryption

### At Rest
- **Algorithm**: AES-256
- **Key Storage**: AWS KMS (Key Management Service)
- **Rotation**: Keys rotated every 90 days

### OpenAI API Keys
```javascript
// How we handle your API key:
1. Stored ONLY in browser localStorage
2. Never transmitted to Codexa servers
3. NEVER logged or stored in server databases
4. Requests sent directly from browser to OpenAI
```

---

## 5. API Security

### Rate Limiting
- **Free**: 3 requests/minute, 90,000 tokens/month
- **Pro**: 60 requests/minute, unlimited tokens
- **Enterprise**: Custom limits

### Authentication
- Session tokens expire after 30 days
- Multi-factor authentication (MFA) available on Pro+
- API keys use Bearer token authorization

### CORS & CSRF Protection
- CORS headers restrict cross-origin requests
- CSRF tokens protect form submissions
- Content Security Policy (CSP) headers enforced

---

## 6. User Permissions & Access Control

### File Sharing (Pro+)
- **Permissions**: Owner, Editor, Viewer
- **Link Security**: Long random URLs, no guessing
- **Expiration**: Optional - set custom expiration dates

### Team Collaboration (Enterprise)
- **Roles**: Admin, Editor, Viewer, Guest
- **Audit Logs**: All actions tracked with timestamps
- **SSO/SAML**: Enterprise authentication support

---

## 7. Third-Party Services

### Services We Use

| Service | Purpose | Data Shared |
|---------|---------|-------------|
| **OpenAI** | AI Chat | Code snippets, queries |
| **Stripe** | Payments | Payment info only |
| **AWS** | Infrastructure | None (encrypted storage) |
| **Sentry** | Error Tracking | Error logs, analytics |
| **Auth0** | Authentication | Email, name (optional) |

### Third-Party Security
- All partners are SOC 2 Type II certified
- Data processing agreements signed with each
- Regular security audits conducted

---

## 8. User Rights & Responsibilities

### Your Rights
- **Right to Access**: Download all your data anytime
- **Right to Delete**: Delete your account and all data
- **Right to Export**: Export code in standard formats
- **Right to Privacy**: Full transparency about our practices

### Your Responsibilities
- **API Key Security**: Keep your OpenAI API key private
- **Password Security**: Use strong, unique passwords
- **Browser Security**: Keep your browser updated
- **Malware Protection**: Use antivirus software

---

## 9. Compliance & Certifications

### Standards We Follow
- ✅ GDPR (General Data Protection Regulation)
- ✅ CCPA (California Consumer Privacy Act)
- ✅ SOC 2 Type II
- ✅ ISO 27001 (In progress)

### Data Residency
- **Default**: AWS US-East-1
- **EU**: Data stored in AWS EU region
- **Custom**: Available for Enterprise customers

---

## 10. Incident Response

### What Happens if There's a Breach?

1. **Detection** - 24/7 security monitoring
2. **Investigation** - Immediate forensic analysis
3. **Notification** - Users notified within 72 hours
4. **Mitigation** - Affected systems taken offline
5. **Resolution** - Root cause fixed, security hardened

### Security Team
- **Response Time**: <1 hour for critical issues
- **On-Call**: 24/7 security team coverage
- **Contact**: security@codexa.ai

---

## 11. Privacy Controls

### Account Settings

**Data Collection**
```
Privacy Settings
├── Analytics - ON/OFF
├── Error Reports - ON/OFF
├── Usage Tracking - ON/OFF
└── Email Communications - ON/OFF
```

**Data Export**
```
Export Your Data
├── Download Account Data (JSON)
├── Export All Code Files
├── Download Chat History
└── Export Usage Statistics
```

**Account Deletion**
```
Delete Account
├── Delete all personal data
├── Retain/delete code files
├── Cancel subscription
└── Confirmation required
```

---

## 12. Cookies & Tracking

### Essential Cookies (Required)
- `session_id` - Keeps you logged in
- `csrf_token` - Security protection

### Optional Cookies (Analytics)
- `analytics_id` - Track features you use
- `preferences` - Your editor settings

### Disabling Tracking
1. Go to Settings → Privacy
2. Toggle "Analytics" to OFF
3. Clear existing cookies

### Do Not Track
We honor "Do Not Track" browser signals automatically.

---

## 13. Children's Privacy

Codexa is not intended for children under 13 years old.

- **Age Restriction**: Must be 13+ to create account
- **Parental Consent**: Required for users 13-18
- **COPPA Compliance**: Children's Online Privacy Protection Act

---

## 14. Updates to Privacy Policy

- **Review Frequency**: Quarterly review
- **Major Changes**: 30-day advance notice via email
- **Notification**: Displayed prominently in app
- **Acceptance**: Continued use = acceptance of changes

### Version History
- **v2.0** - April 26, 2026 - Current
- **v1.5** - January 15, 2026 - Added EU data residency
- **v1.0** - June 1, 2024 - Initial policy

---

## 15. Security Best Practices

### For You
✅ Use strong, unique passwords
✅ Enable two-factor authentication
✅ Keep your browser updated
✅ Don't share your API keys
✅ Review active sessions regularly
✅ Log out on shared computers

### For Enterprises
✅ Use SSO/SAML authentication
✅ Enable IP whitelisting
✅ Configure security policies
✅ Review audit logs monthly
✅ Implement role-based access
✅ Use dedicated support team

---

## 16. Contact & Support

### Privacy Concerns
📧 **Email**: privacy@codexa.ai
📋 **Form**: [Privacy Request](https://codexa.ai/privacy/request)
⏱️ **Response Time**: 7 business days

### Data Subject Requests
Under GDPR/CCPA, you can request:
- **Access**: Get a copy of your data
- **Deletion**: Delete your account
- **Portability**: Export your data
- **Correction**: Fix inaccurate data
- **Restriction**: Limit how we use your data

### Mailing Address
```
Codexa Privacy Team
123 Tech Street
San Francisco, CA 94105
USA
```

### Additional Resources
- 📚 [Data Processing Agreement](https://codexa.ai/dpa)
- 🔐 [Security Policy](https://codexa.ai/security)
- 🛡️ [Compliance Info](https://codexa.ai/compliance)
- 📞 [Contact Us](https://codexa.ai/contact)

---

## 17. Acknowledgments

This privacy policy was created with input from:
- Security experts and consultants
- Privacy advocates and legal counsel
- User feedback and community suggestions
- Industry best practices and standards

---

**By using Codexa, you agree to this Privacy & Security Policy.**

Last Updated: April 26, 2026
Version: 2.0
