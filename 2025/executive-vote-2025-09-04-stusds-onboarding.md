---
title: Template - [Executive Vote] stUSDS Onboarding, USDS-SKY Rewards Normalization, Prime Settlement Cycle, Core Simplification Buffer Budget Transfer, Accessibility Reward Budget Transfer, Spark Proxy Spell - September 4, 2025
summary: Onboard stUSDS with Bounded External Access Module Exception (BEAM), update USDS-SKY Rewards rate, execute Prime Settlement Cycle for Spark and Grove, transfer USDS for Core Simplification Buffer Budget, transfer USDS for Accessibility Reward Budget, execute Spark Proxy Spell.
date: 2025-09-04T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] stUSDS Onboarding, USDS-SKY Rewards Normalization, Prime Settlement Cycle, Core Simplification Buffer Budget Transfer, Accessibility Reward Budget Transfer, Spark Proxy Spell - September 4, 2025

The Governance Facilitators, Dewiz, and Sidestream have placed an executive proposal into the voting system. SKY holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- stUSDS will be onboarded with the actions below.
- The reward rate for USDS-SKY farm will be updated with the actions described below.
- A transfer of TBD will be made to Spark for the Prime Settlement Cycle.
- **8 million USDS** will be transfered to [0xd8507ef0a59f37d15b5d7b630fa6eea40ce4afdd](https://etherscan.io/address/0xd8507ef0a59f37d15b5d7b630fa6eea40ce4afdd) for the Core Simplification Buffer budget.
- **3 million USDS** will be transfered to [0x05F471262d15EECA4059DadE070e5BEd509a4e73](https://etherscan.io/address/0x05F471262d15EECA4059DadE070e5BEd509a4e73) for the Accessibility Reward budget.
- A Spark proxy spell will be executed at TBD.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.powerhouse.io/A.1.9.2.1_Pause_Delay/a98b8227-95f6-4711-9d8d-f52cbc6ad2d0|0db30758e055). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**24 hours**](https://sky-atlas.powerhouse.io/A.1.9.2.1.2_Pause_Delay_Current_Value/09d2514b-3169-4755-a654-2c774456980d|0db30758e055d2d0).

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**. 

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### stUSDS Onboarding

- **Authorization**: [Governance Poll 1562](https://vote.sky.money/polling/QmQwTjgE)  
- **Proposal**: [Forum Post 1](https://forum.sky.money/t/atlas-edit-weekly-cycle-proposal-week-of-2025-09-01/27122), [2](https://forum.sky.money/t/technical-scope-of-the-stusds-module-launch/27129)

If this executive proposal passes, then stUSDS will be onboarded with the parameters detailed below.

#### 

### USDS-SKY Rewards Normalization

- **Authorization**: [Stability Facilitator Approval](https://forum.sky.money/t/sky-token-rewards-usds-to-sky-rewards-normalization-configuration/26638/15)
- **Proposal**: [Forum Post](https://forum.sky.money/t/sky-token-rewards-usds-to-sky-rewards-normalization-configuration/26638/14)

If this executive proposal passes, then $executive_entry_2_implications.

### Prime Settlement Cycle

- **Authorization**: [TBD]()
- **Proposal**: [TBD]()

If this executive proposal passes, then $executive_entry_3_implications.

### Core Simplification Buffer Budget Transfer

- **Authorization**: [Governance Poll 1562](https://vote.sky.money/polling/QmQwTjgE)
- **Proposal**: [Forum Post](https://forum.sky.money/t/atlas-edit-weekly-cycle-proposal-week-of-2025-09-01/27122)

If this executive proposal passes, then $executive_entry_3_implications.

### Accessibility Reward Budget Transfer

- **Authorization**: [Governance Poll 1561](https://vote.sky.money/polling/QmXRwLEu)
- **Proposal**: [Forum Post](https://forum.sky.money/t/utilization-of-the-accessibility-reward-budget-a-2-4/27131)

If this executive proposal passes, then $executive_entry_3_implications.

### Spark Proxy Spell

If this executive proposal passes, then the Prime Agent proxy spell for Spark will be executed at [TBD](), with the following contents. 

#### [Ethereum] Spark USDS Morpho Vault - Onboard November Ethena PTs

- **Authorization**: [Governance Poll 1569](https://vote.sky.money/polling/QmeLKi1N)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

The following November Ethena PTs will be onboarded to the Spark USDS Morpho vault on mainnet.

##### PT-USDe-Nov2025

- Supply cap: **500 million USDS**
- LLTV: **91.5%**
- Oracle:
  - PT value at redemption: **fixed 1 USD**
  - Linear discount rate: **15%**

##### PT-sUSDe-Nov2025

- Supply cap: **500 million USDS**
- LLTV: **91.5%**
- Oracle:
  - PT value at redemption: **fixed 1 USD**
  - Linear discount rate: **15%**

#### [Ethereum] Spark USDC Morpho Vault - Create Vault and Onboard Assets

- **Authorization**: [Governance Poll 1568](https://vote.sky.money/polling/QmXDwbcJ)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

A Spark USDC Morpho vault will be created on mainnet and pools onboarded with the following details:

- Vault name: **Spark Blue Chip USDC Vault**
- Vault ticker: **sparkUSDCbc**
- Admins:
  - Owner: [0x3300f198988e4C9C63F75dF86De36421f06af8c4](https://etherscan.io/address/0x3300f198988e4C9C63F75dF86De36421f06af8c4) (Spark Proxy)
  - Guardian: n/a (defaults to owner)
  - Curator: n/a (defaults to owner)
  - Allocator: [0x8a25A24EDE9482C4Fc0738F99611BE58F1c839AB](https://etherscan.io/address/0x8a25A24EDE9482C4Fc0738F99611BE58F1c839AB) (Spark Liquidity Layer ALM Planner)
- Fee: **1%**
- Markets:
  - cbBTC 86%:
    - Supply cap: **500 million USDC**
  - wstETH 86%:
    - Supply cap: **500 million USDC**


#### [Ethereum] Spark Liquidity Layer - Onboard Spark USDC Morpho Vault

- **Authorization**: [Governance Poll 1566](https://vote.sky.money/polling/QmRLrw8X)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

The Spark USDC Morpho vault will be onboarded to the Spark Liquidity Layer on mainnet with the following deposit [rate limits](https://docs.spark.fi/dev/spark-liquidity-layer/spark-alm-controller#rate-limits):

- maxAmount: **50 million USDC**
- slope: **25 million USDC per day**

#### [Ethereum] Spark Liquidity Layer - Onboard Aave aUSDe

- **Authorization**: [Governance Poll 1565](https://vote.sky.money/polling/QmTS1Jw7)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

Aave aUSDe will be onboarded to the Spark Liquidity Layer on mainnet with the following [rate limits](https://docs.spark.fi/dev/spark-liquidity-layer/spark-alm-controller#rate-limits):

- Deposits:
  - maxAmount: **250 million USDe**
  - slope: **100 million USDe per day**
- Withdrawals:
  - maxAmount: **Unlimited**

#### [Ethereum] Spark Liquidity Layer - Increase Curve Swap Rate Limits

- **Authorization**: [Governance Poll 1563](https://vote.sky.money/polling/QmUKs4Lt)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

The Curve swap [rate limits](https://docs.spark.fi/dev/spark-liquidity-layer/spark-alm-controller#rate-limits) will be increased in the Spark Liquidity Layer on mainnet with the following parameters:

- sUSDS/USDT
  - maxAmount: **5 million**
  - slope: **100 million per day**
  - maxSlippage: **0.25%**
- PYUSD/USDC
  - maxAmount: **5 million**
  - slope: **100 million per day**
  - maxSlippage: **0.1%**

#### [Ethereum] Spark Liquidity Layer - Increase SparkLend spUSDt and spPYUSD Rate Limits

- **Authorization**: [Governance Poll 1564](https://vote.sky.money/polling/QmNbTb5v)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

SparkLend spUSDT and spPYUSD deposit [rate limits](https://docs.spark.fi/dev/spark-liquidity-layer/spark-alm-controller#rate-limits) will be increased in the Spark Liquidity Layer on mainnet with the following parameters:

- SparkLend spUSDT:
  - maxAmount: Increase by 50 million USDT from 50 million USDT to **100 million USDT**
  - slope: Increase by 75 million USDT per day from 25 million USDT per day to **100 million USDT per day**
- SparkLend spPYUSD:
  - maxAmount: Increase by 50 million PYUSD from 50 million PYUSD to **100 million PYUSD**
  - slope: Increase by 75 million PYUSD per day from 25 million PYUSD per day to **100 million PYUSD per day**

#### [Ethereum] Spark Treasury - Transfer BUIDL to Grove

- **Authorization**: [Governance Poll 1567](https://vote.sky.money/polling/QmbSeE7t)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

Residual BUIDL tokens will be transfered from Spark to Grove on mainnet with the following details:

- Recipient address: [0x491EDFB0B8b608044e227225C715981a30F3A44E](https://etherscan.io/address/0x491EDFB0B8b608044e227225C715981a30F3A44E) (Grove ALM Proxy)
- Transfer amount: **900,612.89 BUIDL-I** (all BUIDL-I held in [Spark ALM Proxy](https://etherscan.io/address/0x1601843c5E9bC251A3272907010AFa41Fa18347E))

#### [Ethereum] Spark Treasury - Withdraw USDS and DAI Reserves from SparkLend

- **Authorization**: [Governance Poll 1570](https://vote.sky.money/polling/QmbHt4Vg)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

All accumulated DAI and USDS reserves will be transfered from the SparkLend Collector to the Spark Proxy on mainnet with the following details:

- Sender address: [0xb137E7d16564c81ae2b0C8ee6B55De81dd46ECe5](https://etherscan.io/address/0xb137E7d16564c81ae2b0C8ee6B55De81dd46ECe5) (SparkLend Collector)
- Recipient address: [0x3300f198988e4C9C63F75dF86De36421f06af8c4](https://etherscan.io/address/0x3300f198988e4C9C63F75dF86De36421f06af8c4) (Spark Proxy)
- Transfer amount: All spDAI and spUSDS in the SparkLend Collector

#### [Ethereum] Spark Treasury - Transfer USDS to Spark Foundation

- **Authorization**: [Atlas](https://sky-atlas.powerhouse.io/A.2.9.1.2.2.5.4.1_Initial_Cash_Grant_To_Spark_Foundation/21ff2ff0-8d73-8018-be75-c28cee3dddb7%7C9e1f80092582d59891b0d93ee881)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/september-4-2025-proposed-changes-to-spark-for-upcoming-spell/27102)

The following transfer of USDS from the Spark SubProxy to the Spark Foundation will be executed:

- Transfer **800,000 USDS** from the Spark SubProxy to the Spark Foundation at [0x92e4629a4510AF5819d7D1601464C233599fF5ec](https://etherscan.io/address/0x92e4629a4510AF5819d7D1601464C233599fF5ec).

## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
