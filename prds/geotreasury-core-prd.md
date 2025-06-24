# Product Requirements Document (PRD): GeoTreasury Core

## 1. Overview

**GeoTreasury Core** is the foundational repository for the GeoTreasury.com platform, responsible for the core logic, Plutus smart contracts (treasury and side contracts), UBI distribution mechanisms, and Cardano blockchain integration. This PRD outlines the requirements, features, and success criteria for the development of the core system, as derived from the project roadmap.

## 2. Purpose & Scope

- **Purpose:**
  - To implement the essential backend logic and smart contracts that enable automated, transparent, and fair UBI distribution funded by e-commerce transactions on Cardano.
- **Scope:**
  - Plutus smart contracts (treasury and side contracts)
  - UBI distribution logic
  - Cardano blockchain integration (eUTXO, transaction monitoring)
  - Oracle integration hooks for randomness (Charli3)
  - Identity verification hooks (Atala PRISM)

## 3. Core Features & Requirements

### 3.1 Plutus Smart Contracts
- **Treasury Contract:**
  - Collects and holds a configurable percentage (2-10%) of e-commerce transactions in ADA.
  - Exposes parameters for UBI allocation percentage and distribution frequency.
  - Provides transaction monitoring and reporting mechanisms.
- **Side Contract:**
  - Manages recipient lists and eligibility.
  - Integrates with Charli3 Oracle for verifiable random selection of UBI recipients.
  - Supports efficient multi-recipient distribution.

### 3.2 UBI Distribution Logic
- Monthly (or configurable interval) selection of recipients from a verified pool.
- Batched ADA distribution to selected recipients.
- Audit trails for all distributions, including randomness verification.

### 3.3 Cardano Blockchain Integration
- Use of Cardano's eUTXO model for multi-output transactions.
- Transaction metadata for transparency and notification support.
- Transaction monitoring and event emission for external systems.

### 3.4 Integration Hooks
- **Charli3 Oracle Integration Hooks:**
  - Interfaces for requesting and consuming verifiable random numbers.
  - Audit trail integration for randomness verification.
- **Atala PRISM Integration Hooks:**
  - Interfaces for verifying recipient eligibility (DID, credentials, country restrictions).
  - Credential verification callbacks.

## 4. Non-Functional Requirements

- **Security:**
  - Formal verification of smart contracts.
  - Multi-signature requirements for treasury operations.
  - Rate limiting for distribution transactions.
- **Performance:**
  - Efficient handling of large recipient lists and high transaction volumes.
  - Optimized contract execution costs.
- **Transparency:**
  - All transactions and distributions are publicly auditable.
  - Event emission for external monitoring and reporting.
- **Scalability:**
  - Support for Hydra Layer-2 integration (future phase).

## 5. Success Criteria

- Smart contracts successfully deployed and functional on Cardano testnet and mainnet.
- UBI funds are correctly collected, held, and distributed according to parameters.
- Recipient selection is fair, random, and verifiable.
- All transactions and distributions are transparent and auditable.
- System passes formal verification and security audits with no critical vulnerabilities.

## 6. Milestones & Timeline

- **Phase 1:**
  - Treasury contract development and testnet deployment
  - Side contract development and testnet deployment
  - Oracle and identity integration hooks (testnet)
- **Phase 2:**
  - Mainnet deployment of contracts
  - Full integration with e-commerce API and notification systems
  - Event emission and monitoring integration

## 7. Out of Scope

- Frontend user interfaces (handled in frontend repository)
- Merchant SDKs and dashboards (handled in API repository)
- Full Atala PRISM and Charli3 Oracle implementations (only integration hooks required)
- Blockchain explorer integration (handled in reporting repository)
- Automated report generation (handled in reporting repository)

## 8. Risks & Mitigations

- **Smart contract vulnerabilities:** Mitigated by formal verification and third-party audits.
- **Oracle failures:** Fallback and audit mechanisms.
- **Regulatory changes:** Configurable parameters and modular compliance logic.

## 9. Glossary
- **ADA:** Native cryptocurrency of Cardano.
- **eUTXO:** Extended Unspent Transaction Output model.
- **DID:** Decentralized Identifier.
- **UBI:** Universal Basic Income.
- **Plutus:** Cardano's smart contract language.
- **Charli3:** Decentralized oracle for Cardano.
- **Atala PRISM:** Decentralized identity solution for Cardano.

---

This PRD will be updated as the project evolves and as feedback is received from stakeholders and the community. 