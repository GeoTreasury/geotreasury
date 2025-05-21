### Key Points
- Research suggests Atala PRISM allows users to control sharing of email and wallet addresses.
- It seems likely the UBI platform needs user consent to access email for notifications.
- The evidence leans toward wallet addresses being accessible for ADA distribution.

#### Identifying Recipients
The UBI platform uses Atala PRISM, Cardano's decentralized identity system, to select random recipients from its identity registry. This ensures only verified Cardano users with DIDs are eligible for UBI, aligning with the goal of distributing to any Cardano user.

#### Access to Contact Information
For notifications like "someapp.com shared 5 ADA with you," the platform likely needs users' email addresses, which they can choose to share through Atala PRISM with consent. Wallet public addresses, part of the user's identity, are accessible for distributing ADA, as they're linked to the DID.

#### Notification Mechanism
Atala PRISM supports notification features, possibly alerting users via the Atala App or email when data is requested. The platform might include messages in transaction metadata, but standard wallets like Yoroi may not display this to users, suggesting a separate notification system is needed.

---

### Survey Note: Detailed Analysis of Recipient Identification and Notification in the Cardano UBI E-commerce Platform

This survey note provides a comprehensive analysis of how the Cardano UBI E-commerce Platform, as described on [geotreasury.com]([invalid URL, do not cite]), will identify recipients for Universal Basic Income (UBI) distributions and send notifications, focusing on the role of Atala PRISM in managing identities and the mechanisms for accessing email addresses and wallet public addresses. It explores the technical capabilities of Atala PRISM, user privacy considerations, and potential notification strategies, drawing on extensive research and documentation as of May 21, 2025.

#### Background on the UBI Platform and Atala PRISM
The Cardano UBI E-commerce Platform aims to redistribute 5-10% of transaction profits as UBI to random Cardano users, using a Stripe-like e-commerce API on the Cardano blockchain. The platform leverages Atala PRISM, Cardano's decentralized identity solution, for identity verification and potential country restrictions, as outlined in the project description. Atala PRISM, developed by IOHK, enables self-sovereign identity (SSI), allowing users to own and control their digital identities using decentralized identifiers (DIDs) and verifiable credentials (VCs) [Atala PRISM Overview](https://atalaprism.io/). This ensures users have privacy and control over their personal data, which is critical for identifying recipients and sending notifications.

#### Identifying Recipients for UBI Distribution
The project description states that UBI is distributed to "any Cardano user, not just app users," with Cardano’s RNG selecting recipients from Atala PRISM’s identity registry. This implies that the platform relies on Atala PRISM for a list of eligible users, but not all Cardano users may have registered with Atala PRISM, as it's an optional identity solution. Research suggests that Atala PRISM enables users to create DIDs, which are stored in a secure digital wallet, and can be shared with applications like the UBI platform [Learning Cardano - Atala PRISM](https://www.learningcardano.com/atala-prism/). For the platform to distribute UBI, it must access the wallet public addresses linked to these DIDs, which are part of the user's identity and necessary for sending ADA transactions.

To clarify, wallet public addresses are inherently public on the blockchain, but linking them to a user's identity in Atala PRISM requires the user's consent, as Atala PRISM prioritizes privacy. The platform can use the Atala PRISM registry to select random recipients, assuming they have registered their identities, and distribute ADA to their wallet addresses. This process is supported by Cardano's transaction capabilities, where the UBI Treasury Smart Contract, written in Plutus, can execute transfers to these addresses [Cardano Stack Exchange - How does Atala Prism work?](https://cardano.stackexchange.com/questions/201/how-does-atala-prism-work).

#### Access to Email Addresses for Notifications
The user query specifically asks whether the UBI platform will have access to recipients' email addresses for sending notifications, such as "someapp.com shared 5 ADA with you," as mentioned in the project description. Research indicates that Atala PRISM allows users to store various types of personal data, including email addresses, as part of their digital identity [Built on Cardano - Atala PRISM](https://builtoncardano.com/atala-prism). However, users have complete control over what data they share, and the platform can only access email addresses with explicit user consent.

For example, when users register with Atala PRISM, they can choose to include their email address and specify whether they want to share it with specific applications for notification purposes. This is consistent with Atala PRISM's design, which emphasizes self-sovereign identity, allowing users to "choose who their data is shared with" [Atala PRISM (ADA) on Cardano Cube](https://www.cardanocube.io/projects/atala-prism). Therefore, for the UBI platform to send email notifications, recipients must have opted into sharing their email addresses, likely during registration or through a specific consent process within Atala PRISM.

#### Access to Wallet Public Addresses
Wallet public addresses are a different matter, as they are part of the user's identity in Atala PRISM and necessary for distributing ADA. Research suggests that wallet addresses are linked to the user's DID, and since the platform needs to send ADA to these addresses, it will have access to them as part of the identity verification process [Atala PRISM: Foundations for Sovereignty | AdaPulse](https://adapulse.io/atala-prism-foundations-for-sovereignty/). Unlike email addresses, wallet addresses are public on the blockchain, but Atala PRISM ensures that the link between the address and the user's identity is controlled, maintaining privacy unless shared.

For UBI distribution, the platform can use the wallet addresses directly from the Atala PRISM registry, as this is a standard part of the identity for blockchain transactions. This access does not require additional consent beyond the user's registration with Atala PRISM, as the wallet address is inherently part of the transaction process.

#### Notification Mechanism and Atala PRISM Features
The project description mentions that recipients get ADA "plus a message," suggesting a notification system. Research into Atala PRISM's capabilities reveals that it supports notification features, particularly for data requests. For instance, a Reddit post from 2021 discusses how the Atala App might receive notifications when a service requests access to user data, such as a credit score, and the user can approve or deny [Reddit - Atala Prism, Credit Scores, and NFT](https://www.reddit.com/r/cardano/comments/ny7cgd/atala_prism_credit_scores_and_nft/). This suggests that Atala PRISM can notify users through its app or potentially via email, depending on the contact information shared.

However, for UBI distributions, where the platform selects random recipients, it's unclear if users need to opt-in for notifications. Given Atala PRISM's privacy focus, it's likely that users must consent to receive notifications, possibly by sharing their email addresses or enabling notifications within the Atala App. Alternatively, the platform could include the message in the transaction metadata, as Cardano supports this feature [Build with transaction metadata | Cardano Developer Portal](https://developers.cardano.org/docs/transaction-metadata/). For example, metadata can include descriptive data, such as a message, and is stored on the blockchain forever [How to create a metadata transaction using cardano-wallet | Cardano Developer Portal](https://developers.cardano.org/docs/transaction-metadata/how-to-create-a-metadata-transaction-wallet/).

#### Challenges with Wallet Display of Metadata
Research into popular Cardano wallets, such as Yoroi, indicates that standard wallets may not display transaction metadata in a user-friendly way. For instance, guides on using Yoroi wallet, such as those from Altcoin Buzz and CoinBureau, focus on sending, receiving, and staking ADA, but do not mention metadata display [How To Use The Yoroi Wallet - Bitcoin & Crypto Guide - Altcoin Buzz](https://www.altcoinbuzz.io/bitcoin-and-crypto-guide/how-to-use-the-yoroi-wallet/), [Yoroi Wallet Review 2025: How to use the Yoroi Wallet](https://coinbureau.com/review/yoroi-wallet-review/). This suggests that for random Cardano users, seeing the UBI message might require them to use a specialized application or check transaction details on a blockchain explorer, which may not be practical for all users.

Given this, the platform likely needs a separate notification system, such as email, which again requires users to have shared their contact information with consent. This aligns with the project's open-source nature and community-driven approach, potentially integrating with services like Chainlink for off-chain notifications, as seen in other blockchain ecosystems [Trigger Smart Contract Execution Using Chainlink Automation | Chainlink](https://chain.link/education/automation).

#### Practical Implementation and User Consent
For practical implementation, the UBI platform would likely require users to opt-in for notifications when registering with Atala PRISM or through a separate process. For example, users could specify in their Atala PRISM profile that they are willing to receive UBI notifications, sharing their email address for this purpose. The platform would then use Cardano’s RNG to select recipients from this subset, ensuring compliance with privacy laws like GDPR, given Atala PRISM's regulatory compliance by design [Atix Labs - Atala PRISM](https://www.atixlabs.com/atala-prism).

However, the project's goal of distributing to "any Cardano user" suggests a broader reach, which may conflict with the need for consent. It's possible that the platform assumes users registered with Atala PRISM have implicitly agreed to potential UBI distributions, but notifications would still require explicit consent for contact information. This ambiguity highlights the need for clear documentation, which was not fully available in the search results, suggesting the project may still be in early development.

#### Comparative Analysis with Other Blockchains
Compared to Ethereum, where smart contracts can emit events for notifications via services like Push.org, Cardano's eUTXO model requires more explicit off-chain integration due to its transaction-based architecture [Token Transfer Notification from Smart Contract | Tutorial | Push Notifications | Push Documentation](https://push.org/docs/developers/tutorials/token-transfer-notification/). Atala PRISM's notification features provide a Cardano-specific solution, but the reliance on user consent for email access is similar to other decentralized identity systems, ensuring privacy but potentially limiting reach.

#### Table: Comparison of Data Access for UBI Distribution and Notifications

| **Data Type**          | **Access Method**                              | **User Consent Required** | **Use Case**                     |
|-------------------------|-----------------------------------------------|---------------------------|-----------------------------------|
| Wallet Public Address   | Part of Atala PRISM DID, accessible for ADA distribution | No, inherent to identity  | Distribute UBI to recipients      |
| Email Address           | Stored in Atala PRISM, shared with consent    | Yes, explicit consent needed | Send notification messages        |
| Notification Mechanism  | Atala App or email, depending on user choice  | Yes, for contact sharing   | Alert recipients about UBI shares |

#### Conclusion
In conclusion, the UBI platform will use Atala PRISM to identify recipients from its identity registry and distribute ADA to their wallet public addresses, which are accessible as part of the user's DID. For notifications, such as "someapp.com shared 5 ADA with you," the platform will need access to users' email addresses, which can only be obtained with explicit user consent through Atala PRISM. Atala PRISM's notification features, such as alerts in the Atala App, can facilitate this, but standard wallet display of transaction metadata may not be sufficient for all users, suggesting a need for a separate notification system. This approach ensures user privacy while enabling the platform to meet its social impact goals, though the exact mechanism may depend on further development and community input.

### Key Citations
- [Atala PRISM Overview](https://atalaprism.io/)
- [Learning Cardano - Atala PRISM](https://www.learningcardano.com/atala-prism/)
- [Built on Cardano - Atala PRISM](https://builtoncardano.com/atala-prism)
- [Atala PRISM (ADA) on Cardano Cube](https://www.cardanocube.io/projects/atala-prism)
- [Atala PRISM: Foundations for Sovereignty | AdaPulse](https://adapulse.io/atala-prism-foundations-for-sovereignty/)
- [Cardano Stack Exchange - How does Atala Prism work?](https://cardano.stackexchange.com/questions/201/how-does-atala-prism-work)
- [Reddit - Atala Prism, Credit Scores, and NFT](https://www.reddit.com/r/cardano/comments/ny7cgd/atala_prism_credit_scores_and_nft/)
- [Build with transaction metadata | Cardano Developer Portal](https://developers.cardano.org/docs/transaction-metadata/)
- [How to create a metadata transaction using cardano-wallet | Cardano Developer Portal](https://developers.cardano.org/docs/transaction-metadata/how-to-create-a-metadata-transaction-wallet/)
- [How To Use The Yoroi Wallet - Bitcoin & Crypto Guide - Altcoin Buzz](https://www.altcoinbuzz.io/bitcoin-and-crypto-guide/how-to-use-the-yoroi-wallet/)
- [Yoroi Wallet Review 2025: How to use the Yoroi Wallet](https://coinbureau.com/review/yoroi-wallet-review/)
- [Trigger Smart Contract Execution Using Chainlink Automation | Chainlink](https://chain.link/education/automation)
- [Token Transfer Notification from Smart Contract | Tutorial | Push Notifications | Push Documentation](https://push.org/docs/developers/tutorials/token-transfer-notification/)
- [Atix Labs - Atala PRISM](https://www.atixlabs.com/atala-prism)