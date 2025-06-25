Core → API → Identity → Randomness → Frontend → Notifications → Reporting → Scalability

Phase 1: Foundation (Start Here)
1. GeoTreasury Core - START WITH THIS
Why first: This is the foundation of the entire platform. Everything else depends on it.
Smart contracts (treasury and side contracts)
UBI distribution logic
Cardano blockchain integration
Integration hooks for other components

2. GeoTreasury API - Second Priority
Why second: Merchants need this to start processing payments and funding the UBI treasury.
Payment processing endpoints
Merchant integration SDKs
UBI allocation logic
Depends on: Core (smart contracts)

3. GeoTreasury Identity - Third Priority
Why third: Recipients need identity verification before they can receive UBI.
DID management
Credential verification
Eligibility checks
Depends on: Core (integration hooks)
Phase 2: Distribution & User Experience

4. GeoTreasury Randomness - Fourth Priority
Why fourth: Needed for fair UBI recipient selection.
Charli3 Oracle integration
Verifiable randomness for recipient selection
Depends on: Core (smart contracts)

5. GeoTreasury Frontend - Fifth Priority
Why fifth: Users need interfaces to interact with the platform.
Recipient onboarding UI
Merchant dashboards
Community governance
Depends on: Core, API, Identity, Randomness
Phase 3: Enhancement & Scale

6. GeoTreasury Notifications - Sixth Priority
Why sixth: Important for user engagement but not critical for MVP.
Multi-channel notifications
Delivery confirmation
Depends on: Core, Frontend

7. GeoTreasury Reporting - Seventh Priority
Why seventh: Transparency is important but can be added after core functionality.
Automated report generation
Blockchain explorer integration
Depends on: Core, API

8. GeoTreasury Scalability - Eighth Priority
Why eighth: Only needed when the platform scales significantly.
Hydra Heads integration
Layer-2 solutions
Depends on: Core, API

9. GeoTreasury Docs - Ongoing
Why ongoing: Documentation should be developed alongside each repository.
API guides
Integration instructions
User manuals