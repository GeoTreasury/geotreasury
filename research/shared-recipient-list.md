### Key Points
- Research suggests a side contract can manage a shared UBI recipient list, ensuring coordinated distributions.
- It seems likely that apps can pull from this list monthly, simplifying randomness and enhancing fairness.
- The evidence leans toward feasibility, given Cardano’s support for multiple transaction outputs, though list size may limit scalability.

### Direct Answer

**Overview**  
You can use a side contract to manage a shared list of Universal Basic Income (UBI) recipients for your Cardano UBI E-commerce Platform, where apps using geotreasury.com pull from this list each month for distributions. This approach can coordinate efforts across apps, ensuring consistent and fair UBI distribution.

**How It Works**  
Each month, the side contract, a separate Plutus smart contract on Cardano, would generate a large list of recipients by randomly selecting from the Atala PRISM identity registry, possibly using an oracle like Charli3 for randomness. Apps integrated with geotreasury.com can then query this list to distribute their 2-10% UBI contributions to the same set of recipients, ensuring everyone on the list benefits from all apps’ distributions that month.

**Technical Feasibility**  
Cardano transactions support multiple outputs, allowing the side contract to distribute UBI to many recipients in one transaction, limited by a 16KB size cap. For example, if each output is about 80 bytes, you could handle around 200 recipients per transaction, splitting into multiple transactions if needed for larger lists.

**Benefits and Considerations**  
This method reduces the need for each app to request randomness, potentially lowering costs, and ensures coordinated distribution, which might be seen as fairer. However, it could limit the total number of unique recipients over time, as only those on the monthly list receive UBI. Transparency is maintained, as all transactions are recorded on the public Cardano blockchain ([Cardano Explorer](https://explorer.cardano.org/)).

---

### Comprehensive Analysis of Using a Side Contract for Shared UBI Recipient List Management

This analysis explores the feasibility and implications of implementing a side contract in the Cardano UBI E-commerce Platform, as described on [geotreasury.com]([invalid url, do not cite]), to manage a shared list of Universal Basic Income (UBI) recipients. The side contract would be updated monthly with a large list of recipients, from which all apps using geotreasury.com would pull for their distributions. It delves into the technical mechanisms, integration with Atala PRISM, randomness generation, transaction feasibility, and potential benefits and challenges, drawing on web search results and inferred details as of 02:19 PM CDT on Wednesday, May 21, 2025.

#### Background on the Platform
The Cardano UBI E-commerce Platform, pitched by Micheal Giles on X, aims to create a decentralized e-commerce system on the Cardano blockchain, redistributing 2-10% of transaction profits as UBI to random Cardano users. The platform provides a Stripe-like API for ADA payments, supporting one-off purchases and subscriptions, similar to Square’s functionality. A Plutus smart contract manages the UBI treasury, collecting profits and distributing them to recipients selected randomly from the Atala PRISM identity registry, with optional country restrictions. The project is open-source, licensed under MIT, and relies on community funding through [Project Catalyst]([invalid url, do not cite]), avoiding profit-taking for operations, as confirmed by the user’s preference.

Currently, each business or developer deploys their own instance of the UBI treasury smart contract, with configurable parameters like UBI percentage (within 2-10%) and country restrictions, selecting recipients independently using randomness provided by oracles like Chainlink or Charli3. The user proposes a side contract that centralizes this process, updating a shared recipient list monthly, from which all apps pull for their distributions.

#### Feasibility of a Side Contract for Shared Recipient List
The user’s proposal involves creating a side contract, an additional Plutus smart contract on Cardano, dedicated to managing a shared list of UBI recipients. This contract would be updated each month with a large list of randomly selected recipients, and apps using geotreasury.com would query this list to distribute their UBI contributions. This approach shifts from independent selection by each app to a coordinated, centralized list, potentially enhancing fairness and efficiency.

##### Technical Implementation
- **Side Contract Structure**: The side contract would be a Plutus smart contract with a state that includes the current month’s recipient list, possibly stored as a datum associated with a UTXO. The list could contain recipient addresses and their eligibility status, verified through Atala PRISM.
- **Monthly Update Process**: Each month, the side contract would trigger an update, selecting a new list of recipients. This selection would use randomness, likely sourced from an oracle like Charli3 or Chainlink, to ensure fairness and unpredictability. The contract would query the Atala PRISM registry to filter eligible users based on country restrictions and then use the random number to select a subset.
- **App Integration**: Apps integrated with geotreasury.com would query the side contract to retrieve the current month’s recipient list. This could be done via a transaction that spends a UTXO with the list datum, returning a new UTXO with the same list for other apps to access. Each app would then distribute its own UBI amount to the recipients on the list, executing their own transactions with multiple outputs.

##### Randomness Generation
Since Cardano smart contracts are deterministic and cannot generate random numbers on-chain, the side contract would rely on external oracles for randomness. Previous discussions highlighted Charli3 as a native Cardano oracle, offering a pay-per-request pull oracle model using $C3 tokens. The side contract would request a random number from Charli3, verify the cryptographic proof, and use it to select recipients from the Atala PRISM registry, ensuring different lists each month.

##### Transaction Feasibility
Cardano transactions support multiple outputs, allowing the side contract or apps to distribute UBI to many recipients in one transaction, limited by the maximum transaction size of 16KB. Research into Cardano transaction limits, such as from [Cardano Stack Exchange](https://cardano.stackexchange.com/questions/216/is-there-a-maximum-number-of-transactions-a-block-can-hold), indicates that the total size includes inputs, outputs, and metadata. Each output, typically sending ADA to a recipient address, is estimated at 50-100 bytes, with a conservative estimate of 80 bytes per output.

- **Size Calculation**: Assuming 2 inputs (e.g., from the treasury) at 100 bytes each, and 500 bytes for metadata and other data, the remaining space for outputs is 16384 - 600 = 15784 bytes. At 80 bytes per output, this allows for 15784 / 80 = 197.3, or about 197 outputs per transaction. For larger lists, distributions can be split into multiple transactions, each handling up to 197 recipients.
- **Practical Example**: If the side contract selects 10,000 recipients monthly, it could distribute in approximately 10,000 / 197 ≈ 51 transactions, each with 197 outputs, which is feasible given Cardano’s low transaction fees and 20-second block time.

##### Benefits of the Approach
- **Coordination Across Apps**: All apps distribute to the same set of recipients each month, ensuring consistency and fairness. Each recipient on the list receives UBI from every app that distributes, potentially increasing the total amount they receive.
- **Efficiency**: The side contract only needs one randomness request per month, reducing oracle costs compared to each app requesting independently. For example, if each request costs 0.55 ADA (as estimated previously), monthly costs are 0.55 ADA, versus potentially higher if each app requests separately.
- **Scalability**: By centralizing the list, the platform can manage large recipient pools more efficiently, with distributions batched into multiple transactions if needed. Cardano’s Hydra protocol could further enhance scalability for high transaction volumes, as mentioned in related discussions.
- **Transparency**: All transactions, including updates to the side contract and distributions, are recorded on the public Cardano blockchain ([Cardano Explorer](https://explorer.cardano.org/)), ensuring verifiability by stakeholders.

##### Challenges and Considerations
- **List Size and Distribution**: If the list is large (e.g., 10,000 recipients), distributing to all in one transaction is infeasible due to size limits, requiring multiple transactions. This increases transaction fees, though Cardano’s low fees mitigate this. For example, at 0.2 ADA per transaction fee, 51 transactions cost 10.2 ADA, which is manageable for monthly distributions.
- **Centralization Concerns**: While the side contract centralizes recipient selection, each app still handles its own distribution, maintaining decentralization in fund management. However, reliance on a single list might reduce diversity, as only listed recipients receive UBI that month, potentially excluding others.
- **Sybil Attacks**: To prevent users from creating multiple identities to increase selection chances, Atala PRISM’s identity verification must be robust, ensuring one DID per real user. The side contract should enforce this during list generation.
- **Regulatory Compliance**: Managing a shared list must comply with data privacy laws like GDPR, ensuring user consent for identity data sharing, especially given Atala PRISM’s decentralized nature.

#### Comparison with Current Design
Currently, each app deploys its own UBI treasury smart contract, selecting recipients independently using randomness and distributing their own 2-10% profits. This allows for flexibility in country restrictions and UBI percentages but may lead to overlap, where some recipients are selected by multiple apps, while others receive none. The side contract approach centralizes selection, ensuring all apps distribute to the same list, potentially enhancing equity but limiting the total number of unique recipients over time.

#### Table: Comparison of Approaches

| **Aspect**            | **Current Design (Independent Selection)** | **Proposed Side Contract (Shared List)** |
|-----------------------|-------------------------------------------|------------------------------------------|
| Recipient Selection   | Each app selects independently, using oracle | Side contract selects monthly list, all apps use |
| Randomness Requests   | Each app requests per distribution         | One request per month by side contract    |
| Distribution Equity   | Potential overlap, some recipients get multiple, others none | All listed recipients get from all apps, consistent |
| Scalability          | Each app handles own distribution, may scale poorly with many apps | Centralized list, batched distributions, potentially more scalable |
| Transparency         | Public blockchain, but selections vary by app | Public blockchain, single list ensures uniform verifiability |
| Cost                 | Higher oracle costs with multiple requests | Lower, single oracle request per month   |

#### Conclusion
Implementing a side contract to manage a shared UBI recipient list is feasible within the Cardano ecosystem, leveraging its support for multiple transaction outputs and low transaction fees. The side contract would update monthly with a randomly selected list from Atala PRISM, using an oracle for fairness, and apps would pull from this list for their distributions. This approach enhances coordination, reduces oracle costs, and ensures consistent distribution across apps, though it requires managing list size within transaction limits and addressing centralization concerns. Transparency is maintained through public blockchain records, aligning with the platform’s open-source, community-driven mission.

### Key Citations
- [Universal basic income on blockchain: the case of circles UBI](https://www.frontiersin.org/journals/blockchain/articles/10.3389/fbloc.2024.1362939/full)
- [Proof of Humanity](https://proofofhumanity.id/)
- [Is there a maximum number of transactions a block can hold?](https://cardano.stackexchange.com/questions/216/is-there-a-maximum-number-of-transactions-a-block-can-hold)
- [Max number of transaction inputs](https://forum.cardano.org/t/max-number-of-transaction-inputs/60023)
- [Understanding Unspent Transaction Outputs (UTXO) in the Cardano Blockchain](https://emurgo.io/understanding-unspent-transaction-outputs-in-cardano/)
- [Cardano Explorer](https://explorer.cardano.org/)
- [Charli3 Official Website](https://charli3.io/)