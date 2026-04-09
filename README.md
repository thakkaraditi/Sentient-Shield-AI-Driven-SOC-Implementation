# Sentient-Shield-AI-Driven-SOC-Implementation
Project Overview: A theoretical and practical implementation of a Security Operations Center (SOC) using Wazuh and MITRE ATT&amp;CK mapping. This project was developed during a technical internship at Infotact Solutions.
Collaboration: Cyber Defense Operations Center (CDOC) Team
Subject: Full-Scale IAM & Zero Trust Implementation

1. Phase 1: Infrastructure & Identity Core
Establishing the foundational environment and the identity hierarchy for the "Infotact" organization.
Deployment: Dockerized Keycloak with a production-ready PostgreSQL backend.
Realm Management: Creation of the organizational realm and administrative security settings.

<img width="956" height="323" alt="keylock dockerized" src="https://github.com/user-attachments/assets/310383e9-76e8-43a0-87cb-4391d91b593c" />

Figure 1: Successful Docker orchestration for database and app.

<img width="959" height="477" alt="infotact relam" src="https://github.com/user-attachments/assets/04a733e1-fe7a-49e6-bb2c-e13f436629cb" />

Figure 2: Infotact Realm successfully initialized.

<img width="1391" height="620" alt="authentication admin" src="https://github.com/user-attachments/assets/c065df2d-f2ea-4239-8a5b-d227e78716d4" />

Figure 3: Admin Console Authentication configuration.

2. Phase 2: Client Registration & SSO Integration
Integrating the web portal into the identity provider using the OpenID Connect (OIDC) protocol.
Client Management: Configuration of nexus-portal with specific redirect URIs (localhost:5000).
SSO Validation: Verifying the handshake between the Python Flask backend and the Keycloak server.

<img width="1396" height="235" alt="clients" src="https://github.com/user-attachments/assets/aae35e25-fdb7-484c-8272-dff59f26f2ed" />

Figure 4: Registered OIDC Client inventory.

<img width="956" height="295" alt="python is running" src="https://github.com/user-attachments/assets/ed5ce3d6-cbf0-4995-aa91-c11f517b7682" />

Figure 5: Python Flask server handling authentication redirects.

<img width="1422" height="645" alt="authentication client" src="https://github.com/user-attachments/assets/132e993a-84b0-4cb3-8cee-f7fd71a62cf7" />

Figure 6: Redirection flow to Client Authentication port

3. Phase 3: RBAC & Advanced Group Mapping
Implementing granular access control through Realm Roles, Client Roles, and Group memberships.
Role Hierarchy: Establishing roles (ADMIN, DEVELOPER, VIEWER) at both Realm and Client levels.
Token Mappers: Configuring Protocol Mappers to ensure group memberships are included in the JWT (Access Token).

<img width="953" height="477" alt="rules created" src="https://github.com/user-attachments/assets/f28ab9da-d49a-4dc0-89aa-5ee691e42be7" />

Figure 7: Defined Realm Roles for the organization.

<img width="1227" height="607" alt="client role" src="https://github.com/user-attachments/assets/62d5ad70-b857-41b0-81dd-1bd2ee08e04e" />

Figure 8: Client-specific roles assigned to nexus-portal.
<img width="1423" height="503" alt="groups" src="https://github.com/user-attachments/assets/4ae5911b-f72f-4838-92a5-7f64197de846" />

Figure 9: Group structure for Engineering and Admin departments.

<img width="1383" height="346" alt="mapper" src="https://github.com/user-attachments/assets/9aa3383d-8800-4fcb-b167-6a69cb560b91" />

Figure 10: Protocol Mapper configuration for Group membership claims.





4. Phase 4: Security Hardening & MFA
Enforcing Zero Trust principles through Multi-Factor Authentication and Brute Force protection.
Identity Verification: Implementation of TOTP (Time-based One-Time Password) via mobile authenticators.
Policy Enforcement: Activation of account lockout policies to prevent credential stuffing.

<img width="959" height="482" alt="mobile authentication otp enabled" src="https://github.com/user-attachments/assets/0929d7aa-5ec9-47ed-b27e-29dc8a35416b" />

Figure 11: Mandatory MFA setup for new user registration.

<img width="958" height="449" alt="for security brute force detection enabled" src="https://github.com/user-attachments/assets/5f3e6d4a-952e-4d59-9618-2accdf41d1c7" />

Figure 12: Brute Force detection and security defense settings.


5. Phase 5: Testing & Final Results
Validation of the end-to-end flow, from login to role-specific content access.
User Provisioning: Verifying active users and their mapped roles.
Access Verification: Successful extraction of groups in the application landing page.

<img width="959" height="455" alt="user created" src="https://github.com/user-attachments/assets/002e14df-415e-4d79-9b0c-3a9e0350f9ab" />

Figure 13: Active user account overview.

<img width="956" height="447" alt="roles mapped" src="https://github.com/user-attachments/assets/ad189cc9-9262-45fd-b5cd-85f1bb139cc3" />

Figure 14: User role mapping and assignment overview.
<img width="959" height="296" alt="accessing group sucessfull (1)" src="https://github.com/user-attachments/assets/9efd7411-318d-406c-a153-3e506a6d7051" />

Figure 15: Final success page showing authorized group access.


6. Final Audit & Logs
Reviewing the operational logs to ensure all security events are being captured correctly.

<img width="959" height="437" alt="events captured sucess" src="https://github.com/user-attachments/assets/41f57f4b-30d7-4df7-88c8-5dd0d1897d71" />

Figure 16: Event audit trail showing successful logins and code-to-token exchanges.

<img width="959" height="478" alt="nexus portal" src="https://github.com/user-attachments/assets/a672e254-4bc7-4654-aaa3-517399ba2f75" />

Figure 17: Active session management and IP tracking.

Conclusion
The NexusAuth ZT project successfully demonstrates the deployment of a modern, Zero Trust Identity and Access Management (IAM) framework. By integrating Keycloak with a Flask-based web architecture, the team has established a security environment where "trust" is never assumed and must be verified at every layer.

Key Outcomes:
Centralized Identity Governance: The transition from localized user management to a centralized PostgreSQL-backed Keycloak instance ensures a single, authoritative source of truth for all organizational identities.

Multi-Layered Defense: By enforcing TOTP-based Multi-Factor Authentication (MFA) and Brute Force Detection, the system is resilient against common credential-based attacks, including automated stuffing and unauthorized login attempts.

Granular Authorization: Through the implementation of Role-Based Access Control (RBAC) and Group Mapping, the project ensures that users—such as those in the Engineering group—only access the resources necessary for their specific roles, effectively minimizing the internal attack surface.

Operational Visibility: The activation of comprehensive Event Auditing and session tracking provides the security team with the real-time visibility required to detect and respond to anomalies instantaneously.

Future Outlook:
Moving forward, this infrastructure provides a scalable foundation for adding Single Sign-On (SSO) across additional corporate applications and implementing Context-Aware Access (based on IP reputation or device posture). This project marks a significant step in hardening the organization’s digital perimeter and aligning with international cybersecurity standards.
