# Section 8: Security by Design

## Tổng quan

Security by Design không phải là việc "thêm bảo mật vào cuối" — mà là tư duy bảo mật phải được tích hợp từ giai đoạn thiết kế đầu tiên. Section này đi sâu vào kiến trúc bảo mật, threat modeling, và các kỹ thuật nâng cao mà mọi software engineer cần nắm vững.

> **Lưu ý:** Section 3.10 đã cover các nguyên tắc bảo mật cơ bản (input validation, encryption basics, secure defaults). Section 8 đi **sâu hơn nhiều** vào kiến trúc, threat modeling, authentication/authorization patterns, và secure coding practices ở production-grade.

## Triết lý cốt lõi

```
"Security is not a feature. It's a property of the entire system."
— Ross Anderson
```

Ba nguyên tắc nền tảng:

1. **Defense in Depth** — Nhiều lớp bảo vệ, không phụ thuộc vào một lớp duy nhất
2. **Least Privilege** — Chỉ cấp quyền tối thiểu cần thiết
3. **Fail Secure** — Khi hệ thống lỗi, phải fail về trạng thái an toàn (deny by default)

## Mục lục

### [8.1 Threat Modeling](./8.1-Threat-Modeling.md)
- STRIDE framework và cách áp dụng thực tế
- Data Flow Diagrams cho threat identification
- Attack trees và risk assessment
- Walkthrough: threat modeling cho TypeScript web app
- Threat modeling trong design process

### [8.2 Authentication Deep Dive](./8.2-Authentication-Deep-Dive.md)
- OAuth 2.0 flows (Authorization Code + PKCE, Client Credentials, Device Code)
- OpenID Connect (ID tokens, userinfo, scopes)
- JWT deep dive: RSA vs HMAC, token rotation, storage strategies
- Session-based vs token-based auth
- MFA: TOTP, WebAuthn/Passkeys
- Machine-to-machine authentication (API keys, mTLS)

### [8.3 Authorization Patterns](./8.3-Authorization-Patterns.md)
- RBAC, ABAC, ReBAC (Google Zanzibar model)
- Permission systems design (Casbin, CASL, custom engine)
- Row-level security
- Multi-tenancy authorization
- API authorization: scopes, permissions, resource-level checks

### [8.4 Secure Coding Practices](./8.4-Secure-Coding-Practices.md)
- OWASP Top 10 deep dive với TypeScript prevention code
- CSP, CORS, Security Headers
- Rate limiting và brute force protection
- File upload security
- Dependency & supply chain security
- Secrets management

## Ai nên đọc Section này?

| Vai trò | Focus |
|---------|-------|
| **Junior Developer** | 8.4 (Secure Coding) trước, rồi 8.2-8.3 |
| **Senior Developer** | Tất cả, đặc biệt 8.1 (Threat Modeling) |
| **Tech Lead / Architect** | 8.1 trước, rồi 8.3 (Authorization Patterns) |
| **Security Engineer** | Toàn bộ section như reference |

## Công cụ bảo mật được đề cập

- **Static Analysis:** ESLint security plugins, SonarQube, Semgrep
- **Dependency Scanning:** npm audit, Snyk, Socket.dev
- **Secret Scanning:** GitLeaks, TruffleHog
- **Penetration Testing:** OWASP ZAP, Burp Suite
- **Auth Providers:** Auth0, Keycloak, Firebase Auth
- **Authorization:** Casbin, CASL, OpenFGA (Zanzibar)
- **Secrets Management:** HashiCorp Vault, AWS Secrets Manager

## Nguyên tắc khi đọc

1. **Không có "secure enough"** — Bảo mật là continuous process
2. **Code examples là production-grade** — Copy-paste được, nhưng cần hiểu context
3. **Threat model trước khi code** — Hiểu attack surface trước khi viết defense
4. **Test security** — Security không test được = không tồn tại
