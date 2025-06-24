# Product Requirements Document (PRD): GeoTreasury Frontend

## 1. Overview

**GeoTreasury Frontend** is the user-facing repository for the GeoTreasury.com platform, responsible for the web and mobile interfaces that enable recipient onboarding, merchant dashboards, and community governance. This PRD outlines the requirements, features, and success criteria for the development of the frontend system, as derived from the project roadmap.

## 2. Purpose & Scope

- **Purpose:**
  - To provide an intuitive, secure, and accessible user interface for all platform participants, including recipients, merchants, and community members.
- **Scope:**
  - Recipient onboarding flows (identity verification, wallet association, consent management)
  - Merchant dashboards (transaction tracking, analytics, integration management)
  - Community governance portal (voting, proposals, transparency tools)
  - User interface hooks for notification preferences and transparency reporting

## 3. Core Features & Requirements

### 3.1 Recipient Onboarding
- Streamlined user experience for identity verification (Atala PRISM integration)
- Wallet address association (QR code scanning, manual entry)
- Consent management for data sharing
- Notification preferences setup (multi-channel)
- Multilingual and mobile-first design
- Region-specific verification workflows

### 3.2 Merchant Dashboard
- Transaction tracking and analytics
- UBI contribution and impact reporting
- Integration management for e-commerce APIs/SDKs
- Customization options for UBI allocation
- Merchant onboarding and support resources

### 3.3 Community Governance
- Voting mechanisms for proposals and treasury management
- Proposal creation and discussion tools
- Community oversight and transparency reporting
- Impact measurement dashboards

## 4. Non-Functional Requirements

- **Security:**
  - Secure authentication and authorization (OAuth 2.0, DID-based login)
  - Protection of user data and privacy
- **Performance:**
  - Fast load times and responsive UI
  - Real-time updates for transactions and notifications
- **Accessibility:**
  - Mobile-first, progressive web app (PWA) design
  - Internationalization (i18n) and localization support
- **Usability:**
  - Intuitive navigation and user flows
  - Comprehensive onboarding and help resources
- **Scalability:**
  - Support for growing user base and feature set

## 5. Success Criteria

- Onboarding completion rate above 80%
- Merchant retention rate above 85%
- Community governance participation above 10% of users
- User satisfaction score above 4.5/5
- All critical user flows function correctly across devices and languages

## 6. Milestones & Timeline

- **Phase 1:**
  - Recipient onboarding UI and wallet association
  - Merchant dashboard MVP
  - Community governance portal MVP
- **Phase 2:**
  - Advanced analytics and reporting
  - Multilingual and accessibility enhancements

## 7. Out of Scope

- Backend smart contract logic (handled in core repository)
- Oracle and identity provider implementations (only frontend integration required)
- E-commerce API/SDK development (integration only)
- Notification delivery system (handled in notifications repository)
- Automated report generation (handled in reporting repository)

## 8. Risks & Mitigations

- **User onboarding friction:** Addressed by streamlined flows and comprehensive help resources.
- **Security vulnerabilities:** Mitigated by secure authentication and regular audits.
- **Accessibility gaps:** Continuous testing and user feedback.

## 9. Glossary
- **DID:** Decentralized Identifier.
- **PWA:** Progressive Web App.
- **UBI:** Universal Basic Income.
- **Atala PRISM:** Decentralized identity solution for Cardano.
- **OAuth 2.0:** Industry-standard authentication protocol.

---

This PRD will be updated as the project evolves and as feedback is received from stakeholders and the community. 