# Sentient-Shield-AI-Driven-SOC-Implementation
Project Overview: A theoretical and practical implementation of a Security Operations Center (SOC) using Wazuh and MITRE ATT&amp;CK mapping. This project was developed during a technical internship at Infotact Solutions.
Collaboration: Cyber Defense Operations Center (CDOC) Team
Subject: Full-Scale IAM & Zero Trust Implementation

1. Phase 1: Infrastructure & Identity Core
Establishing the foundational environment and the identity hierarchy for the "Infotact" organization.
Deployment: Dockerized Keycloak with a production-ready PostgreSQL backend.
Realm Management: Creation of the organizational realm and administrative security settings.

Figure 1: Successful Docker orchestration for database and app.

Figure 2: Infotact Realm successfully initialized.

Figure 3: Admin Console Authentication configuration.

2. Phase 2: Client Registration & SSO Integration
Integrating the web portal into the identity provider using the OpenID Connect (OIDC) protocol.
Client Management: Configuration of nexus-portal with specific redirect URIs (localhost:5000).
SSO Validation: Verifying the handshake between the Python Flask backend and the Keycloak server.

Figure 4: Registered OIDC Client inventory.

Figure 5: Python Flask server handling authentication redirects.

Figure 6: Redirection flow to Client Authentication portal.

3. Phase 3: RBAC & Advanced Group Mapping
Implementing granular access control through Realm Roles, Client Roles, and Group memberships.
Role Hierarchy: Establishing roles (ADMIN, DEVELOPER, VIEWER) at both Realm and Client levels.
Token Mappers: Configuring Protocol Mappers to ensure group memberships are included in the JWT (Access Token).

Figure 7: Defined Realm Roles for the organization.

Figure 8: Client-specific roles assigned to nexus-portal.
Figure 9: Group structure for Engineering and Admin departments.

Figure 10: Protocol Mapper configuration for Group membership claims.





4. Phase 4: Security Hardening & MFA
Enforcing Zero Trust principles through Multi-Factor Authentication and Brute Force protection.
Identity Verification: Implementation of TOTP (Time-based One-Time Password) via mobile authenticators.
Policy Enforcement: Activation of account lockout policies to prevent credential stuffing.

Figure 11: Mandatory MFA setup for new user registration.

Figure 12: Brute Force detection and security defense settings.




5. Phase 5: Testing & Final Results
Validation of the end-to-end flow, from login to role-specific content access.
User Provisioning: Verifying active users and their mapped roles.
Access Verification: Successful extraction of groups in the application landing page.

Figure 13: Active user account overview.

Figure 14: User role mapping and assignment overview.

Figure 15: Final success page showing authorized group access.


6. Final Audit & Logs
Reviewing the operational logs to ensure all security events are being captured correctly.

Figure 16: Event audit trail showing successful logins and code-to-token exchanges.

Figure 17: Active session management and IP tracking.
