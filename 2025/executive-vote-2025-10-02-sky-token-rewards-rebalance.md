---
title: Template - [Executive Vote] SKY Token Rewards Rebalance, Whitelist Keel ALM Proxy, Execute Prime Agent Proxy Spells - October 2, 2025
summary: Normalize SKY Token Rewards, whitelist Keel ALM Proxy on the LitePSM, execute Proxy Spells for Spark, Grove, and Keel Prime Agents. 
date: 2025-10-02T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] SKY Token Rewards Rebalance, Whitelist Keel ALM Proxy, Execute Prime Proxy Spells - October 2, 2025

The Governaance Facilitators, dewiz, and Sidestream have placed an executive proposal into the voting system. SKY holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- The reward rate for the USDS-SKY farm will be updated with the actions described below.
- The Keel Mainnet ALM Controller will be whitelisted on the LitePSM. 
- Prime Agent proxy spells for Spark, Grove, and Keel will be executed.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.powerhouse.io/A.1.9.2.1_Pause_Delay/a98b8227-95f6-4711-9d8d-f52cbc6ad2d0|0db30758e055). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**$number hours**](https://sky-atlas.powerhouse.io/A.1.9.2.1.2_Pause_Delay_Current_Value/09d2514b-3169-4755-a654-2c774456980d|0db30758e055d2d0).

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**. 

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### SKY Token Rewards Rebalance

- **Authorization**: [Forum Post](https://forum.sky.money/t/sky-token-rewards-usds-to-sky-rewards-normalization-configuration/26638/20), [Atlas](https://sky-atlas.powerhouse.io/A.4.3.2.1_SKY_Token_Rewards/1d6f2ff0-8d73-809b-9088-d11181182d17%7Cb3417d54eb16)
- **Proposal**: [Forum Post](https://forum.sky.money/t/sky-token-rewards-usds-to-sky-rewards-normalization-configuration/26638/19)

If this executive proposal passes, then the distribution of SKY token rewards to USDS holders will be normalized to ensure the effective yield provided by these rewards equals the Sky Savings Rate (SSR), as per [A.4.3.2 - Token Reward Mechanism](https://sky-atlas.powerhouse.io/A.4.3.2_Token_Reward_Mechanism/2e3e7014-bd66-4e85-b915-b86ae3ceeb16%7Cb3417d54), by executing the following actions:

- `yank()` MCD_VEST_SKY_TREASURY vest with ID 6.
- Distribute the remaining tokens from the old DssVest by calling `VestedRewardsDistribution.distribute()` on REWARDS_DIST_USDS_SKY.
- Create a new MCD_VEST_SKY_TREASURY stream with the following parameters:
  - `res`: 1 (restricted)
  - Increase SKY allowance for MCD_VEST_SKY_TREASURY to the sum of all active streams and the new stream created by this executive vote.
  - `vestBgn`: `block.timestamp`
  - `vestTau`: `block.timestamp` + 15,724,800 seconds (182 days after the spell executes)
  - `tot`: **68,379,376 SKY**
- File the new stream ID on REWARDS_DIST_USDS_SKY

### Whitelist Keel ALM Proxy on litePSM

- **Authorization**: [Governance Poll 1596](https://vote.sky.money/polling/QmWfqZRS)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-02-2025-prime-technical-scope-keel-initialization-for-upcoming-spell/27192)

If this executive proposal passes, then the Keel ALM Proxy will be whitelisted on the LitePSM with the following call:

- "MCD_LITE_PSM_USDC_A.kiss(0xa5139956eC99aE2e51eA39d0b57C42B6D8db0758)"

### Prime Agent Proxy Spells 

If this executive proposal passes, then Prime Agent proxy spells for Spark, Grove, and Keel will be executed at [TBD]($TBD), [0x67e7b3bFAb1Fb6267baECEc034Bbf7592F6B4E9b](0x67e7b3bFAb1Fb6267baECEc034Bbf7592F6B4E9b) and [0x7ae136b7e677C6A9B909a0ef0a4E29f0a1c3c7fE](https://etherscan.io/address/0x7ae136b7e677C6A9B909a0ef0a4E29f0a1c3c7fE) respectively, with the following contents.

#### Spark Proxy Spell

##### [Ethereum] Spark USDS Morpho Vault - Increase PT-USDe-27Nov Supply Cap

- **Authorization**: [Governance Poll 1592](https://vote.sky.money/polling/QmXYRjmQ)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-spark-for-upcoming-spell/27191)

The [PT-USDe-27Nov2025 pool](https://morpho.blockanalitica.com/ethereum/markets/8cdb63a27a48ac27fadc0f158a732104bcc4e10bb61c9a5095ea7c127204e26c/) supply cap will be increased by 500 million USDS from 500 million USDS to **1 billion USDS**.

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

#####

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)


#### Grove Proxy Spell

##### [Mainnet + Plume] Grove Liquidity Layer - Plume Deployment

- **Authorization**: [Governance Poll 1594](https://vote.sky.money/polling/QmPsHirj)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

The Grove Liquidity Layer will be deployed to Plume with the following contract addresses and parameters:

###### Contract Addresses

- Grove Governance: plume:[0x3048386E09c72C20FB268a37d2B630D7f2Ee9138](https://explorer.plume.org/address/0x3048386E09c72C20FB268a37d2B630D7f2Ee9138)

- Receiver: plume:[0x7D592085847558A97695DDC1CD6E8FEe818510E8](https://explorer.plume.org/address/0x7D592085847558A97695DDC1CD6E8FEe818510E8)

- ALM Controller: plume:[0x0C462Fff7Cc975bC9F2B0aEB8270febA5FD71e1B](https://explorer.plume.org/address/0x0C462Fff7Cc975bC9F2B0aEB8270febA5FD71e1B)
- ALM Proxy: plume:[0x1DB91ad50446a671e2231f77e00948E68876F812](https://explorer.plume.org/address/0x1DB91ad50446a671e2231f77e00948E68876F812)
- ALM Rate Limits: plume:[0x7f8408eBbBC3504F83eeDa52910dd75Eba92C955](https://explorer.plume.org/address/0x7f8408eBbBC3504F83eeDa52910dd75Eba92C955)

- Relayer: plume:[0x0eEC86649E756a23CBc68d9EFEd756f16aD5F85f](https://explorer.plume.org/address/0x0eEC86649E756a23CBc68d9EFEd756f16aD5F85f)
- Freezer: plume:[0xB0113804960345fd0a245788b3423319c86940e5](https://explorer.plume.org/address/0xB0113804960345fd0a245788b3423319c86940e5)

###### Parameters

- Plume.GROVE_EXECUTOR.delay = **0 days**
- Plume.GROVE_EXECUTOR.gracePeriod = **7 days**


##### [Mainnet + Plume] Grove Liquidity Layer - Onboard Apollo ACRDX

- **Authorization**: [Governance Poll 1595](https://vote.sky.money/polling/QmTE1YTn)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2-2025-proposed-changes-to-grove-for-upcoming-spell/27190)

Apollo ACRDX will be onboarded to the Grove Liquidity Layer on Plume. A risk assessment for this deployment has been produced and can be found [here](https://forum.sky.money/t/anemoy-tokenized-apollo-diversified-credit-fund-risk-assessment/27186).

###### Associated DAO Resolution

Sky Governance approved the DAO Resolution authorizing the subscription to the Anemoy Tokenized Apollo Diversified Credit Fund by Aspen Grove Ltd with the IPFS hash [bafkreiefed2vyibzwd7ajacaezuq5r422z4zoo4lnbk3ximd5mzktwjzfi](https://gateway.pinata.cloud/ipfs/bafkreiefed2vyibzwd7ajacaezuq5r422z4zoo4lnbk3ximd5mzktwjzfi).

###### [Plume] Apollo ACRDX [Rate Limits](https://sky-atlas.powerhouse.io/A.2.3.9.1.1.1.1.2_Rate_Limits/264f2ff0-8d73-8050-892b-e4a0ed9828dc|9e1ff936a6cb63b1903ca2d845de)

* ACRDX: plume:[0x354a9222571259457B2e98b2285B62e6a9bf4eD3](https://explorer.plume.org/address/0x354a9222571259457B2e98b2285B62e6a9bf4eD3)
  * Deposits:
    * Max amount: **20 million USDC**
    * Slope: **20 million USDC per day**
  * Withdrawals:
    * Max amount: **Unlimited**

###### [Mainnet and Plume] JTRSY Transfer and Redemption [Rate Limits](https://sky-atlas.powerhouse.io/A.2.3.9.1.1.1.1.2_Rate_Limits/264f2ff0-8d73-8050-892b-e4a0ed9828dc|9e1ff936a6cb63b1903ca2d845de)

Grove will be redeeming JTRSY on Plume for the USDC liquidity necessary to purchase 50M of ACRDX. The following rate parameters will be necessary to transfer JTRSY shares to Plume and redeem it for USDC.

###### [Mainnet] LIMIT_CENTRIFUGE_TRANSFER [Rate Limits](https://sky-atlas.powerhouse.io/A.2.3.9.1.1.1.1.2_Rate_Limits/264f2ff0-8d73-8050-892b-e4a0ed9828dc|9e1ff936a6cb63b1903ca2d845de)

- JTRSY token: eth:[0xFE6920eB6C421f1179cA8c8d4170530CDBdfd77A](https://etherscan.io/address/0xFE6920eB6C421f1179cA8c8d4170530CDBdfd77A)
- Plume destinationCentrifugeId: **4**
    * Max amount: **20 million JTRSY**
    * Slope: **20 million JTRSY per day**

###### [Mainnet] setCentrifugeRecipient

- centrifugeId: **4**
- receipient: Plume.ALM_PROXY

###### JTRSY Withdrawl [Rate Limits](https://sky-atlas.powerhouse.io/A.2.3.9.1.1.1.1.2_Rate_Limits/264f2ff0-8d73-8050-892b-e4a0ed9828dc|9e1ff936a6cb63b1903ca2d845de)

- JTRSY token: plume:[0x818A3593340622c1D6A51B039e191F2f8C99A1F2](https://explorer.plume.org/address/0x818A3593340622c1D6A51B039e191F2f8C99A1F2)
- Max amount: **20 million USDC**
- Slope: **20 million USDC per day**

#### Keel Proxy Spell

##### Initialize Keel Mainnet ALM Controller

- **Authorization**: [Governance Poll 1596](https://vote.sky.money/polling/QmWfqZRS)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-02-2025-prime-technical-scope-keel-initialization-for-upcoming-spell/27192)

The Keel ALM controller will be initialized on mainnet with the following addresses and rate limit parameters:

###### Contract Addresses

- ALM Proxy: [0xa5139956eC99aE2e51eA39d0b57C42B6D8db0758](https://etherscan.io/address/0xa5139956eC99aE2e51eA39d0b57C42B6D8db0758)
    - admin: [Keel Subproxy](https://etherscan.io/address/0x355CD90Ecb1b409Fdf8b64c4473C3B858dA2c310)
- RateLimits: [0x65E7B39e508944F7C4278d3e4580f84Eb20b26a7](https://etherscan.io/address/0x65E7B39e508944F7C4278d3e4580f84Eb20b26a7)
    - admin: [Keel Subproxy](https://etherscan.io/address/0x355CD90Ecb1b409Fdf8b64c4473C3B858dA2c310)
- ALM Controller: [0xEF26BDc34F35669C235345aeF24A251B1EE80EF3](https://etherscan.io/address/0xEF26BDc34F35669C235345aeF24A251B1EE80EF3)
    - admin: [Keel Subproxy](https://etherscan.io/address/0x355CD90Ecb1b409Fdf8b64c4473C3B858dA2c310)
    - proxy: ALM Proxy listed above
    - rateLimits_: RateLimits listed above
    - vault_: [ALLOCATOR_NOVA_A_VAULT](https://etherscan.io/address/0xe4470dd3158f7a905cdea07260551f72d4bb0e77)
    - psm_: [MCD_LITE_PSM_USDC_A](https://etherscan.io/address/0xf6e72db5454dd049d0788e411b06cfaf16853042)
    - daiUsds_: [DAI_USDS](https://etherscan.io/address/0x3225737a9bbb6473cb4a45b7244aca2befdb276a)
    - cctp_: [CCTP Token Messenger](https://etherscan.io/address/0xbd3fa81b58ba92a82136038b25adec7066af3155)

###### [Rate Limit](https://sky-atlas.powerhouse.io/A.2.3.9.1.1.1.1.2_Rate_Limits/264f2ff0-8d73-8050-892b-e4a0ed9828dc|9e1ff936a6cb63b1903ca2d845de) Parameters

- **LIMIT_USDS_MINT**:
    - Max amount: **10,000 USDS** (Onboarding)
    - Slope: **5,000 USDS per day**
- **LIMIT_USDS_TO_USDC**:
    - Max amount: **10,000 USDS** (Onboarding)
    - Slope: **5,000 USDS per day**
- **sUSDS (LIMIT_4626_DEPOSIT) Deposits**:
    - Max amount: **10,000 sUSDS** (Onboarding)
    - Slope: **5,000 sUSDS per day**
- **sUSDS (LIMIT_4626_WITHDRAW) Withdrawals**:
    - Max amount: **Unlimited**

## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
