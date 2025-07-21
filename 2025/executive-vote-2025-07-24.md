---
title: Template - [Executive Vote] MKR-to-SKY Phase Three, Sky Token Rewards Rebalance, Aligned Delegate Compensation for June 2025, Atlas Core Development Payments for July 2025, HVB DAO Resolution, Spark Transfer of BUIDL and JTRSY Tokens to Grove, Star Proxy Spells - July 24, 2025
summary: MKR-to-SKY phase three, Sky Token Rewards rebalance, Aligned Delegate compensation for June 2025, Atlas Core Development USDS and SKY payments for July 2025, Huntington Valley Bank DAO Resolution, Spark transfer of BUIDL and JTRSY tokens to Grove, Star proxy spells.
date: 2025-07-24T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] MKR-to-SKY Phase Three, Sky Token Rewards Rebalance, Aligned Delegate Compensation for June 2025, Atlas Core Development Payments for July 2025, HVB DAO Resolution, Spark Transfer of BUIDL and JTRSY Tokens to Grove, Star Proxy Spells - July 24, 2025

The Governance Facilitators, Sidestream and Dewiz have placed an executive proposal into the voting system. SKY Holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- MKR-to-SKY Upgrade Phase Three actions will be executed.
- Actions to rebalance the Sky Token Reward will be executed.
- A total of **21,062 USDS** will be distributed as Aligned Delegate compensation for June 2025.
- A total of **77,584 USDS** and **618,000 SKY** will be distributed as Atlas Core Development payments for July 2025.
- A Huntington Valley Bank DAO Resolution will be approved.
- A tokenized T-bills transfer from Spark to Grove will be executed.
- Star proxy spells for Spark and Grove will be executed.

### Execute Spark Proxy Spell

- **Authorization**: [Ecosystem Approval](https://forum.sky.money/t/may-29-2025-proposed-changes-to-spark-for-upcoming-spell/26372/3)
- **Proposal**: [Forum Post](https://forum.sky.money/t/may-29-2025-proposed-changes-to-spark-for-upcoming-spell/26372)

If this executive proposal passes, then a Spark Proxy Spell will be executed at [0x3968a022D955Bbb7927cc011A48601B65a33F346](https://etherscan.io/address/0x3968a022D955Bbb7927cc011A48601B65a33F346) with the following contents.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.powerhouse.io/#A.1.8.2.1_Pause_Delay-a98b8227-95f6-4711-9d8d-f52cbc6ad2d0|0db30758e055). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**24 hours**](https://sky-atlas.powerhouse.io/#A.1.8.2.1.2_Pause_Delay_Current_Value-09d2514b-3169-4755-a654-2c774456980d|0db30758e055d2d0).

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**.

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### MKR-to-SKY Upgrade Phase Three

- **Authorization**: [Atlas](https://sky-atlas.powerhouse.io/A.4.1.2.1.4.2.2_Offboard_Borrowing_Against_Staked_MKR/1f1f2ff0-8d73-8024-bf88-f0a17374ceea%7Cb341f4c0b83472dc1f9e1a3b)
- **Proposal**: [Forum Post](https://forum.sky.money/t/phase-3-mkr-to-sky-migration-items-july-24th-spell/26750)

If this executive proposal passes, then the following actions will complete Phase Three of the MKR-to-SKY Upgrade.

#### Offboard LSE-MKR-A (legacy [Seal Engine](https://info.sky.money/collateral/seal-engine))

- Increase LSE-MKR-A liquidation ratio by 9,875 percentage points from 125% to **10,000%**.
- Reduce LSE-MKR-A `chop` by 8 percentage points from 8% to **0%**.

### Sky Token Rewards Rebalance

- **Authorization**: [Ecosystem Approval](https://forum.sky.money/t/sky-token-rewards-usds-to-sky-rewards-normalization-configuration/26638/9)
- **Proposal**: [Forum Post](https://forum.sky.money/t/sky-token-rewards-usds-to-sky-rewards-normalization-configuration/26638/8)

If this executive proposal passes, then the distribution of SKY token rewards to USDS holders will be normalized to ensure the effective yield provided by these rewards equals the Sky Savings Rate (SSR), as per [A.4.3.2 - Token Reward Mechanism](https://sky-atlas.powerhouse.io/A.4.3.2_Token_Reward_Mechanism/2e3e7014-bd66-4e85-b915-b86ae3ceeb16%7Cb3417d54), by executing the following actions:

- Yank MCD_VEST_SKY_TREASURY vest with ID 4.
- Claim the remaining tokens from the old DssVest by calling `VestedRewardsDistribution.distribute()` on REWARDS_DIST_USDS_SKY.
- Create a new MCD_VEST_SKY_TREASURY stream with the following parameters:
  - res: 1 (restricted)
  - vestBgn: block.timestamp
  - vestTau: block.timestamp + 15,724,800 seconds (182 days after the spell executes)
  - Vesting rate: 100,851,495 * WAD SKY
  - File the new stream ID on REWARDS_DIST_USDS_SKY

### Aligned Delegate Compensation for June 2025

- **Authorization**: [Atlas](https://sky-atlas.powerhouse.io/Budget_And_Participation_Requirements/4c698938-1a11-4486-a568-e54fc6b0ce0c%7C0db3af4e)
- **Proposal**: [Forum Post](https://forum.sky.money/t/june-2025-aligned-delegate-compensation/26816)

If this executive proposal passes, then a total of **21,062 USDS** will be distributed to eight Aligned Delegates as compensation for June 2025 as follows:

| Delegate    | Amount (USDS) | Address                                                                                                               |
|-------------|--------------:|-----------------------------------------------------------------------------------------------------------------------|
| BLUE        | 4,000         | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |
| Bonapublica | 4,000         | [0x167c1a762B08D7e78dbF8f24e5C3f1Ab415021D3](https://etherscan.io/address/0x167c1a762B08D7e78dbF8f24e5C3f1Ab415021D3) |
| Cloaky      | 4,000         | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |
| JuliaChang  | 4,000         | [0x252abAEe2F4f4b8D39E5F12b163eDFb7fac7AED7](https://etherscan.io/address/0x252abAEe2F4f4b8D39E5F12b163eDFb7fac7AED7) |
| WBC         | 3,733         | [0xeBcE83e491947aDB1396Ee7E55d3c81414fB0D47](https://etherscan.io/address/0xeBcE83e491947aDB1396Ee7E55d3c81414fB0D47) |
| PBG         | 800           | [0x8D4df847dB7FfE0B46AF084fE031F7691C6478c2](https://etherscan.io/address/0x8D4df847dB7FfE0B46AF084fE031F7691C6478c2) |
| Excel       | 400           | [0x0F04a22B62A26e25A29Cba5a595623038ef7AcE7](https://etherscan.io/address/0x0F04a22B62A26e25A29Cba5a595623038ef7AcE7) |
| AegisD      | 129           | [0x78C180CF113Fe4845C325f44648b6567BC79d6E0](https://etherscan.io/address/0x78C180CF113Fe4845C325f44648b6567BC79d6E0) |

### Atlas Core Development USDS Payments for July 2025

- **Authorization**: [Ecosystem Authorization](https://forum.sky.money/t/atlas-core-development-payment-requests-july-2025/26779/6), [Atlas Axis Authorization](http://forum.sky.money/t/atlas-core-development-payment-requests-july-2025/26779/5)
- **Proposal**: [Forum Post](https://forum.sky.money/t/atlas-core-development-payment-requests-july-2025/26779)

If this executive proposal passes, then a total of **77,584 USDS** and **618,000 SKY** will be distributed as Atlas Core Development payments for July 2025 as follows:

#### USDS Payments

| Recipient | Amount (USDS) | Address                                                                                                               |
|-----------|--------------:|-----------------------------------------------------------------------------------------------------------------------|
| BLUE      | 50,167        | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |
| Cloaky    | 16,417        | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |
| Kohla     | 11,000        | [0x73dFC091Ad77c03F2809204fCF03C0b9dccf8c7a](https://etherscan.io/address/0x73dFC091Ad77c03F2809204fCF03C0b9dccf8c7a) |

#### SKY Payments

| Recipient | Amount (SKY) | Address                                                                                                               |
|-----------|-------------:|-----------------------------------------------------------------------------------------------------------------------|
| BLUE      | 330,000      | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |
| Cloaky    | 288,000      | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |

### Huntington Valley Bank DAO Resolution

- **Authorization**: [Ecosystem Authorization](https://forum.sky.money/t/huntingdon-valley-bank-transaction-documents-on-permaweb/16264/28)
- **Proposal**: [Forum Post](https://forum.sky.money/t/huntingdon-valley-bank-transaction-documents-on-permaweb/16264/27)

If this executive proposal passes, then the DAO Resolution with IPFS hash [bafkreidm3bqfiwv224m6w4zuabsiwqruy22sjfaxfvgx4kgcnu3wndxmva](https://gateway.pinata.cloud/ipfs/bafkreidm3bqfiwv224m6w4zuabsiwqruy22sjfaxfvgx4kgcnu3wndxmva) will be approved.

### Spark transfer of BUIDL and JTRSY tokens to Grove

- **Authorization**: [Governance Poll 1533](https://vote.sky.money/polling/Qme5qebN)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796#p-103150-mainnet-spark-liquidity-layer-transfer-buidl-and-jtrsy-tokens-to-grove-5)

If this executive proposal passes, then Spark will transfer the existing BUIDL and JTRSY T-bill allocations to Grove by executing the following actions:

- Increase ALLOCATOR-BLOOM-A DC-IAM `gap` by 1.2 billion USDS from 50 million USDS to **1.25 billion USDS**.
- `line` remains unchanged at **2.5 billion USDS**.
- `ttl` remains unchanged at **86400 seconds**.
- Apply ALLOCATOR-BLOOM-A auto-line changes.
- Execute Grove Proxy Spell at address TBC.
- Decrease ALLOCATOR-BLOOM-A `gap` by 1.2 billion USDS from 1.25 billion USDS to 50 million USDS.

Grove ALM Proxy: [0x491EDFB0B8b608044e227225C715981a30F3A44E](https://etherscan.io/address/0x491EDFB0B8b608044e227225C715981a30F3A44E)

### Star Proxy Spells for Spark and Grove

- **Authorization**: [Ecosystem Approval]()
- **Proposal**: [Forum Post]()

If this executive proposal passes, then Star proxy spells for Spark and Grove will be executed at [TBD](https://etherscan.io/address/TBD) and at [TBD](https://etherscan.io/address/TBD) respectively with the following contents.

#### Spark Proxy Spell

##### [Mainnet] SparkLend - Reduce WBTC Liquidation Threshold

- **Authorization**: [Governance Poll 1531](https://vote.sky.money/polling/QmUYJ9YQ)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

Reduce the WBTC [Liquidation Threshold](https://sky-atlas.powerhouse.io/A.AG1.3.2.1.1.1.5_Liquidation_Threshold_Definition/1c1f2ff0-8d73-81ea-bd7e-feb73a44923a%7C7896ed3326389fe3553030cd0a82f68efd49) by 5 percentage points from 40% to **35%**.

##### [Base] Spark Liquidity Layer - Increase Spark USDC Morpho Vault Rate Limits

- **Authorization**: [Governance Poll 1529](https://vote.sky.money/polling/QmSnpq5K)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

Increase the Spark USDC Morpho vault [rate limits](https://docs.spark.fi/dev/spark-liquidity-layer/spark-alm-controller#rate-limits) on Base as follows:

`max`: Increase by 50 million from 50 million to **100 million USDC**.
`slope`: Increase by 25 million per day from 25 million per day to **50 million USDC per day**.

##### [Mainnet] Spark Liquidity Layer - Transfer BUIDL and JTRSY tokens to Grove

- **Authorization**: [Governance Poll 1533](https://vote.sky.money/polling/Qme5qebN)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

Facilitate a Spark transfer of BUIDL and JTRSY tokens to Grove. This requires the above changes at "Spark transfer of BUIDL and JTRSY tokens to Grove" to the ALLOCATOR-BLOOM-A Debt Ceiling Instant Access Module to facilitate the offsetting transfer of USDS from Grove to Spark as Grove will assume the associated debt positions for these collateral tokens.

Additional information about this transfer can be found in [this forum post](https://forum.sky.money/t/tokenized-t-bills-transfer-from-spark-to-grove/26785).

##### [Mainnet] SparkLend - Transfer Accumulated SparkLend ETH to Multisig to be Liquidated

- **Authorization**: [Governance Poll 1532](https://vote.sky.money/polling/QmaLxz19)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

Transfer the accumulated ETH earned from SparkLend's reserve factor to the following multisig to be liquidated into USDS:

Liquidation multisig: [0x2E1b01adABB8D4981863394bEa23a1263CBaeDfC](https://etherscan.io/address/0x2e1b01adabb8d4981863394bea23a1263cbaedfc)

Any received USDS will later be transferred to the Spark Proxy and serve as additional risk capital.

##### [Mainnet] Spark USDS Vault - Onboard PT-SPK-USDS Farm

- **Authorization**: [Governance Poll 1530](https://vote.sky.money/polling/QmP7RB2p)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

Deploy a Spark USDS Morpho Vault and onboarding the PT-SPK-USDS Farm with the following parameters.

###### Vault Parameter Summary

- `Max amount`: **200 million USDS**
- `Slope`: **100 million USDS per day**

###### PT-USDS-24Sep2025

Pool LLTV: **96.5%**
Oracle base value (value at maturity): **1 USDS per PT token**
Oracle discount rate: **15%**
Pool supply cap: **500 million USDS**

#### Grove Proxy Spell

##### [Mainnet] Mint USDS for BUIDL and JTRSY Tokens and Send it to Spark Allocator Buffer

- **Authorization**: [Governance Poll 1533](https://vote.sky.money/polling/Qme5qebN)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

The Grove Allocator will mint and transfer the exact amount of USDS 1:1 to the BUIDL-I balance at the time of Spell execution plus 404,016,484 USDS for the JTRSY balance to the Spark Allocator in order to close the balance related to these tokenized T-bill holdings.

##### [Mainnet] Grove Liquidity Layer - Onboard BlackRock BUIDL-I

- **Authorization**: [Governance Poll TBD](https://vote.sky.money/polling/TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

Onboard BlackRock BUIDL-I on the Grove Liquidity Layer on Mainnet with the following [rate limit](https://docs.spark.fi/dev/spark-liquidity-layer/spark-alm-controller#rate-limits) parameters:

- Deposits
  - Max amount: **50 million USDC**
  - Slope: **50 million USDC per day**
- Withdrawals
  - Max amount: **Unlimited**

Token address: [0x6a9DA2D710BB9B700acde7Cb81F10F1fF8C89041](https://etherscan.io/token/0x6a9DA2D710BB9B700acde7Cb81F10F1fF8C89041)

##### [Mainnet] Grove Liquidity Layer - Onboard Centrifuge JTRSY

- **Authorization**: [Governance Poll TBD](https://vote.sky.money/polling/TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/july-24-2025-proposed-changes-to-spark-for-upcoming-spell/26796)

Onboard Centrifuge JTRSY on the Grove Liquidity Layer on Mainnet with the following [rate limit](https://docs.spark.fi/dev/spark-liquidity-layer/spark-alm-controller#rate-limits) parameters:

- Deposits
  - Max amount: **50 million USDC**
  - Slope: **50 million USDC per day**
- Withdrawals
  - Max amount: **Unlimited**

Token address: [0x36036fFd9B1C6966ab23209E073c68Eb9A992f50](https://etherscan.io/token/0x36036fFd9B1C6966ab23209E073c68Eb9A992f50)

## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
