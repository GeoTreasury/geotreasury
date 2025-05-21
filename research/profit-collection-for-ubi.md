### Key Points
- Research suggests the platform collects 5-10% of each transaction amount for UBI, not separate fees.
- It seems likely businesses agree to this model, contributing directly from sales.
- The evidence leans toward automatic allocation via multi-output transactions on Cardano.

#### How It Works
When businesses integrate with the geotreasury.com API, they can accept ADA payments for one-off purchases or subscriptions, similar to Square. For each transaction, 5-10% of the payment amount is automatically sent to the UBI treasury, with the rest going to the business. This contribution is built into the transaction, not an additional fee.

#### Profit Collection
The "profits" mentioned are likely the transaction amounts, not the platform's fees. When a customer pays, say, 100 ADA, 5-10 ADA goes to the UBI treasury, and 90-95 ADA goes to the business, ensuring direct support for UBI without extra costs.

#### Handling Subscriptions and Purchases
The API supports both one-off purchases and recurring subscriptions, with the same 5-10% UBI contribution applied to each transaction, making it versatile for e-commerce needs.

---

### Survey Note: Detailed Analysis of Profit Collection in the Cardano UBI E-commerce Platform

This survey note provides a comprehensive analysis of how profit collection works for the Cardano UBI E-commerce Platform, as described on [geotreasury.com](https://geotreasury.com), focusing on how apps integrating with the API facilitate Square-like functionality for handling subscriptions and one-off purchases. It explores the technical mechanisms, business model, and implications for UBI distribution, drawing on information from the project’s X post and inferred details as of 12:10 PM CDT on Wednesday, May 21, 2025.

#### Overview of the Platform
The Cardano UBI E-commerce Platform, pitched by Micheal Giles on X, aims to create a decentralized e-commerce system on the Cardano blockchain, redistributing 5-10% of transaction profits as Universal Basic Income (UBI) to random Cardano users. The platform provides a "Stripe-like API for ADA payments," enabling businesses to accept ADA for various transaction types, including one-off purchases and subscriptions, similar to Square’s functionality. The project is open-source, licensed under MIT, and seeks collaboration and funding through [Project Catalyst](https://projectcatalyst.io).

#### Profit Collection Mechanism
The core question is how exactly the profit collection works, specifically how 5-10% of "transaction profits" is collected and integrated into the API for businesses. The X post by Micheal Giles states: "share 5-10% of transaction profits with random Cardano users," and the landing page summary confirms that "5-10% of profits from the e-commerce platform are collected" into a Plutus smart contract treasury. However, the term "transaction profits" is ambiguous, as it could refer to the platform’s fees, the businesses’ profits, or the transaction amounts themselves.

Research suggests that in the context of payment processing, "profits" likely refer to the fees charged by the platform for transaction processing. However, given the platform’s social good focus and the description, it seems likely that the 5-10% is taken directly from each transaction amount, not as a separate fee. This interpretation is supported by the observation that the X post mentions recipients getting a message like “someapp.com shared 5 ADA with you,” where “someapp.com” is the business, implying the funds come from the business’s transactions, not the platform’s fees.

The evidence leans toward a model where, for each transaction processed through the API, a percentage (5-10%) of the transaction amount is automatically allocated to the UBI treasury. For example, if a customer pays 100 ADA for a product, 5-10 ADA would go to the UBI treasury, and 90-95 ADA would go to the business. This is feasible on Cardano using multi-output transactions, where a single transaction splits the payment between the business’s wallet and the treasury address.

#### API Integration and Square-Like Functionality
The platform’s API is designed to provide Square-like functionality, meaning businesses can integrate it to accept ADA payments seamlessly for both one-off purchases and recurring subscriptions. Square, known for its payment processing and point-of-sale solutions, supports various transaction types, including subscriptions through its billing API. Similarly, the geotreasury.com API would handle:

- **One-Off Purchases**: Businesses can process immediate payments, such as for goods or services, with the 5-10% UBI contribution applied to each transaction.
- **Subscriptions**: For recurring payments, each subscription payment would also have 5-10% allocated to the UBI treasury, ensuring consistency across transaction types.

The API abstracts the complexities of Cardano transactions, allowing businesses to focus on e-commerce without managing blockchain details. This is similar to how Stripe provides RESTful APIs for payment processing, and the platform likely uses Cardano’s payment APIs to facilitate these transactions.

#### Technical Implementation of Profit Collection
Given Cardano’s eUTXO model, transactions are processed as unspent transaction outputs (UTXOs), and smart contracts (Plutus scripts) can enforce rules for fund distribution. The profit collection would work as follows:

1. **Transaction Initiation**: When a customer makes a payment through the business’s integrated API, the transaction amount (X ADA) is specified.
2. **Split Payment**: The Plutus smart contract, part of the API, ensures that Y% (5-10%) of X is sent to the UBI treasury address, and (100 - Y)% is sent to the business’s wallet. This is achieved through a multi-output transaction, a standard feature on Cardano.
3. **Treasury Collection**: The UBI treasury, a Plutus smart contract, collects these funds, which are later distributed to random recipients using Cardano’s RNG and Atala PRISM for identity verification.

This model does not require the platform to charge separate transaction fees; the UBI contribution is built into the transaction itself. This aligns with the project’s open-source, community-driven nature, where businesses agree to this model as part of using the platform, likely motivated by its social impact.

#### Business Model and Incentives
The platform’s business model seems to rely on businesses voluntarily contributing to UBI through their transactions, rather than charging traditional fees. This is unusual for payment processors, which typically charge 2-3% per transaction, but given the project’s focus on equity and social good, it’s plausible. Businesses might be incentivized by:

- **Social Impact**: Contributing to UBI supports displaced workers and aligns with corporate social responsibility goals.
- **Community Support**: As an open-source project, it fosters collaboration and could attract businesses aligned with Cardano’s ecosystem.
- **Low Transaction Costs**: Cardano’s low-fee blockchain reduces operational costs, making the 5-10% contribution more feasible.

However, the exact fee structure is not explicitly stated, and it’s possible the platform sustains itself through other means, such as grants from [Project Catalyst](https://projectcatalyst.io) or donations, given its mention in the X post.

#### Handling Subscriptions and One-Off Purchases
For subscriptions, the API would need to support recurring payments, likely through scheduled transactions or integration with Cardano wallets that handle automatic payments. Each recurring payment would follow the same profit collection model, with 5-10% going to the UBI treasury. This is similar to how Square handles subscriptions through its billing API, ensuring businesses can set up recurring charges with ease.

For one-off purchases, the process is straightforward: each purchase triggers a transaction with the UBI contribution. The platform’s ability to handle both types is crucial for its versatility, catering to various e-commerce needs, from retail to subscription-based services like software-as-a-service (SaaS).

#### Challenges and Considerations
There are challenges to this model, including:

- **Business Adoption**: Businesses might be hesitant to contribute 5-10% of each transaction, especially if margins are tight. The platform would need to demonstrate value, possibly through community support or additional features.
- **Scalability**: High transaction volumes could lead to congestion, though Cardano’s Hydra protocol could help, as mentioned in related discussions.
- **Regulatory Compliance**: Ensuring compliance with financial regulations, especially for UBI distributions, is critical, given the platform’s global reach.

#### Comparative Analysis with Traditional Platforms
Compared to Square or Stripe, which charge fees for payment processing, geotreasury.com’s model is unique in that it integrates UBI contribution directly into transactions. This is more akin to platforms with built-in donation mechanisms, but on a blockchain, ensuring transparency and immutability. The lack of explicit fee details suggests the platform prioritizes social impact over profit, aligning with its open-source ethos.

#### Table: Comparison of Transaction Models

| **Aspect**            | **geotreasury.com**                              | **Square/Stripe**                     |
|-----------------------|--------------------------------------------------|---------------------------------------|
| Fee Structure         | 5-10% of transaction amount to UBI treasury      | 2-3% + fixed fee per transaction      |
| Profit Collection     | Built into transaction, no separate fees         | Fees cover platform costs, no UBI     |
| Transaction Types     | One-off, subscriptions, via ADA payments         | Credit cards, ACH, subscriptions      |
| Social Impact         | Direct UBI contribution to Cardano users         | No built-in social contribution       |

#### Conclusion
In conclusion, the profit collection for the Cardano UBI E-commerce Platform works by automatically allocating 5-10% of each transaction amount to the UBI treasury, with the remaining amount going to the business. This is facilitated through the API, which supports Square-like functionality for one-off purchases and subscriptions, using Cardano’s multi-output transactions. Businesses agree to this model as part of integration, contributing directly from sales to support UBI, aligning with the platform’s social good mission. While the exact fee structure is not detailed, research suggests this approach is feasible, though adoption and scalability remain challenges to monitor.

### Key Citations
- [Project Catalyst funding platform](https://projectcatalyst.io)