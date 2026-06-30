---
title: Template - [Executive Vote] Initialize GROVE Token Rewards, Whitelist New Grove ALMProxy on LitePSM, Add PAU Beacon to Chainlog, Transfer USDS from Amatsu SubProxy to SFF, Update Safe Harbor Agreement, Prime Agent Proxy Spells - July 2, 2026
summary: Initialize GROVE token rewards farm, whitelist the new Grove ALMProxy on LitePSM, add PAU_BEACON to the Chainlog, transfer 14 million USDS from the Amatsu SubProxy to the Sky Frontier Foundation, update the Safe Harbor Agreement, and whitelist Spark, Grove, and Skybase proxy spells.
date: 2026-07-02T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] Initialize GROVE Token Rewards, Whitelist New Grove ALMProxy on LitePSM, Add PAU Beacon to Chainlog, Transfer USDS from Amatsu SubProxy to SFF, Update Safe Harbor Agreement, Prime Agent Proxy Spells - July 2, 2026

The Core Facilitators, Sidestream, and Dewiz have placed an executive proposal into the voting system. SKY holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If this executive proposal passes, then the following actions will occur within the Sky Protocol:

## Executive Summary

- GROVE token rewards for USDS stakers will be initialized.
- The new Grove ALMProxy will be whitelisted on `MCD_LITE_PSM_USDC_A`.
- `PAU_BEACON` will be added to the Chainlog.
- **14 million USDS** will be transferred from Amatsu's SubProxy to Sky Frontier Foundation.
- The Safe Harbor Agreement will be updated.
- Spark, Grove, and Skybase proxy spells will be whitelisted in their respective StarGuard modules.

**Voting for this executive proposal will place your MKR/SKY in support of the changes outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.io/#3c9545d9-775f-4149-88bf-7d297b5302c6). This means that if this executive proposal passes, the changes listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**48 hours**](https://sky-atlas.io/#db442d8a-8d98-47a2-b162-01c2adc22b67).

This executive proposal **has its earliest execution date set to Monday, July 6, 2026 at 18:00 UTC**. This means that it cannot be executed before that date.

This executive proposal includes an office-hours modifier that ensures the proposal can only be executed between 14:00 and 21:00 UTC, Monday through Friday. This is to ensure that at least some auction keepers are available to react to unforeseen market events that may occur as a result of the changes included in this executive proposal.

This executive proposal will be valid for 30 days from its creation. This means that if this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### Initialize GROVE Token Rewards

- **Authorization**: [Governance Poll ID 1639](https://vote.sky.money/polling/Qmd3gCcD)
- **Proposal**: [Technical Scope: Grove Farm](https://forum.skyeco.com/t/technical-scope-grove-farm/27999)

If this executive proposal passes, then a USDS -> GROVE farm will be initialized, enabling users to stake USDS and receive GROVE rewards.

The following actions will occur:

- Add [`0xcBCfCD450de686894d3C5E7E8975cF23EEF077B2`](https://etherscan.io/address/0xcBCfCD450de686894d3C5E7E8975cF23EEF077B2) to the Chainlog as `MCD_VEST_GROVE_TREASURY`.
- Add [`0xB30FE1Cf884B48a22a50D22a9282004F2c5E9406`](https://etherscan.io/address/0xB30FE1Cf884B48a22a50D22a9282004F2c5E9406) to the Chainlog as `GROVE`.
- Initialize the USDS -> GROVE farm with `TreasuryFundedFarmingInit.initFarm` using the following parameters:
  - `stakingToken`: `USDS`
  - `rewardsToken`: `GROVE`
  - `rewards`: [`0x4E41488C19cD35EB4de3083Fc3e204854c75c86a`](https://etherscan.io/address/0x4E41488C19cD35EB4de3083Fc3e204854c75c86a)
  - `rewardsKey`: `"REWARDS_USDS_GROVE"`
  - `dist`: [`0xAf7a108B4fB0b2F65E1Acc9E1a548abe482559C4`](https://etherscan.io/address/0xAf7a108B4fB0b2F65E1Acc9E1a548abe482559C4)
  - `distKey`: `"REWARDS_DIST_USDS_GROVE"`
  - `distJob`: `CRON_REWARDS_DIST_JOB`
  - `distJobInterval`: `7 days - 1 hours`
  - `vest`: `MCD_VEST_GROVE_TREASURY`
  - `vestTot`: 2.45 billion GROVE
  - `vestBgn`: `block.timestamp - 7 days`
  - `vestTau`: 730 days

### Whitelist New Grove ALMProxy on LitePSM

- **Authorization**: [Governance Poll ID 1638](https://vote.sky.money/polling/QmdXjfm6)
- **Proposal**: [July 2, 2026 Proposed Changes to Grove for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-grove-for-upcoming-spell/27976)

If this executive proposal passes, then the new Grove ALMProxy at [`0x0DcD9298e163dFD3c0B5b00F0d9093C36e40A153`](https://etherscan.io/address/0x0DcD9298e163dFD3c0B5b00F0d9093C36e40A153) will be whitelisted on `MCD_LITE_PSM_USDC_A`.

### Add PAU Beacon to Chainlog

- **Authorization**: [Sky Atlas](https://sky-atlas.io/#fd030da6-1a4d-4df6-8e87-043d4b9666d5)
- **Proposal**: [Diamond PAU and Beacon Launch](https://forum.skyeco.com/t/diamond-pau-and-beacon-launch/27997)

If this executive proposal passes, then [`0x829dC2b7E94B1954F0764E573f2E0d45Afa28199`](https://etherscan.io/address/0x829dC2b7E94B1954F0764E573f2E0d45Afa28199) will be added to the Chainlog as `PAU_BEACON`.

### Transfer USDS from Amatsu SubProxy to SFF

- **Authorization**: [Sky Atlas](https://sky-atlas.io/#06bac1e1-ae52-4c67-8ca9-0dcec22dddee)
- **Proposal**: [Technical Scope for Transferring Funds from the SubProxy](https://forum.skyeco.com/t/technical-scope-for-transferring-funds-from-the-subproxy/28004)

If this executive proposal passes, then the following actions will occur:

- [`0x5162489F4FEa651b76c75193387d08aAAC9CB52C`](https://etherscan.io/address/0x5162489F4FEa651b76c75193387d08aAAC9CB52C) will be added to the Chainlog as `SUBPROXY_METHODS`.
- `SUBPROXY_METHODS` will be executed in `AMATSU_SUBPROXY` to transfer **14 million USDS** to Sky Frontier Foundation at [`0xca5183FB9997046fbd9bA8113139bf5a5Af122A0`](https://etherscan.io/address/0xca5183FB9997046fbd9bA8113139bf5a5Af122A0).

### Safe Harbor Update

- **Authorization**: [Sky Atlas - A.2.11.1.2.3 - Safe Harbor Modifications](https://sky-atlas.io/#fcd868db-4a91-4ee0-baf5-1ebd40fc651e)

If this executive proposal passes, then the Safe Harbor Agreement will be updated.

### Spark Proxy Spell

If this executive proposal passes, then a Spark proxy spell with address [`0xcc7529473B850103524905D3914470898aDe8747`](https://etherscan.io/address/0xcc7529473B850103524905D3914470898aDe8747) and codehash `0xf952ba1ea1df8c42217cecd3c4e88abcde2864fbf1e4465b1a13af0bf05e00f0` will be whitelisted in `SPARK_STARGUARD`.

#### Spark Proxy Spell Contents

##### [Ethereum] SparkLend - Set USDC Interest Rate Model to Target Very Low Liquidity

- **Authorization**: [Sky Atlas - A.6.1.1.1.3.2.1.2.1 - SparkLend Risk Parameters Modification](https://sky-atlas.io/#A.6.1.1.1.3.2.1.2.1)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will update the SparkLend USDC interest rate model by deploying a new `RateTargetKinkInterestRateStrategy` and setting it as the USDC reserve interest rate strategy using `PoolConfigurator.setReserveInterestRateStrategyAddress`.

The following SparkLend USDC interest rate parameters will be updated:

- Optimal utilization (`kink`) will be increased from **95%** to **98%**.
- Slope 1 spread above the rate source will be decreased from **125 bps** to **100 bps**.

##### [Ethereum] SparkLend - Claim SparkLend Reserves

- **Authorization**: [Sky Atlas](https://sky-atlas.io/#ea73f176-0b94-4e93-b1ee-ca498ac5a6c6)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will claim all SparkLend reserves. USD stablecoin reserves will be transferred to the ALM Proxy and non-USD reserves will be transferred to the Spark Operations Multisig.

##### [Ethereum] Spark Liquidity Layer - Enable USDT Bridging to Arbitrum

- **Authorization**: [Snapshot Poll 0xcd464acf44fc25d8f5514dd55e4861171eff163256deeea7ab6280b4fa36d342](https://snapshot.box/#/s:sparkdao.eth/proposal/0xcd464acf44fc25d8f5514dd55e4861171eff163256deeea7ab6280b4fa36d342)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will enable USDT bridging from Ethereum to Arbitrum.

The following rate limit parameters will be applied:

- Destination domain: `0x92afd601dfcfc51c04099d77d414d14542677e7a62f04f53c8b74008b30a68f5`
- `maxAmount`: 5 million USDT
- `slope`: 50 million USDT per day

##### [Base] Spark Liquidity Layer - Remove Excess Liquidity

- **Authorization**: [Snapshot Poll 0x4f6d3e7f769d8fe5c7713338274a24bb7932f0fb0d46ce0bc0c0f0087172fa2b](https://snapshot.box/#/s:sparkdao.eth/proposal/0x4f6d3e7f769d8fe5c7713338274a24bb7932f0fb0d46ce0bc0c0f0087172fa2b)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will withdraw all USDS and sUSDS in the Base ALM Proxy back to the Ethereum ALM Proxy.

##### [OP Mainnet] Spark Liquidity Layer - Remove Excess Liquidity

- **Authorization**: [Snapshot Poll 0x4f6d3e7f769d8fe5c7713338274a24bb7932f0fb0d46ce0bc0c0f0087172fa2b](https://snapshot.box/#/s:sparkdao.eth/proposal/0x4f6d3e7f769d8fe5c7713338274a24bb7932f0fb0d46ce0bc0c0f0087172fa2b)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will withdraw all USDS and sUSDS in the OP Mainnet ALM Proxy back to the Ethereum ALM Proxy.

##### [Unichain] Spark Liquidity Layer - Remove Excess Liquidity

- **Authorization**: [Snapshot Poll 0x4f6d3e7f769d8fe5c7713338274a24bb7932f0fb0d46ce0bc0c0f0087172fa2b](https://snapshot.box/#/s:sparkdao.eth/proposal/0x4f6d3e7f769d8fe5c7713338274a24bb7932f0fb0d46ce0bc0c0f0087172fa2b)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will withdraw all USDS and sUSDS in the Unichain ALM Proxy back to the Ethereum ALM Proxy.

##### [Arbitrum] Spark Savings - Deploy spUSDT

- **Authorization**: [Snapshot Poll 0xbf916af7e6765a7d0ebd1d8d09cf58856bac0d46e7c5d597e411fb86f4f7c004](https://snapshot.box/#/s:sparkdao.eth/proposal/0xbf916af7e6765a7d0ebd1d8d09cf58856bac0d46e7c5d597e411fb86f4f7c004)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will deploy `spUSDT` on Arbitrum.

The deployment will use the following parameters:

- `spUSDT` implementation: [`0x282Dafe8b42979e66a90f3e3a6cda8e43F5DD6f0`](https://arbiscan.io/address/0x282Dafe8b42979e66a90f3e3a6cda8e43F5DD6f0)
- `spUSDT`: [`0x45D91340B7e41831b7ef6675f8F0C31f72c3A850`](https://arbiscan.io/address/0x45D91340B7e41831b7ef6675f8F0C31f72c3A850)
- Supply cap: 250 million USDT
- Maximum yield: 6%
- Launch current yield: 0%

##### [Avalanche] Spark Liquidity Layer - Add Timelock and Guardian to Avalanche Governance Bridge

- **Authorization**: [Snapshot Poll 0x5f3a987f3537ca167cccb614c46168e0f04e8cbfc2236c553b2ba5d858a18e22](https://snapshot.box/#/s:sparkdao.eth/proposal/0x5f3a987f3537ca167cccb614c46168e0f04e8cbfc2236c553b2ba5d858a18e22)
- **Proposal**: [July 2, 2026 Proposed Changes to Spark for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-spark-for-upcoming-spell/27982)

If this executive proposal passes, then the Spark proxy spell will add a timelock and guardian to the Avalanche governance bridge.

The following parameters will be used:

- Timelock delay: 3 days
- Planned guardian multisig: [`0x2E1b01adABB8D4981863394bEa23a1263CBaeDfC`](https://snowtrace.io/address/0x2E1b01adABB8D4981863394bEa23a1263CBaeDfC)

### Grove Proxy Spell

If this executive proposal passes, then a Grove proxy spell with address [`0xa21d2E301D50AfF797143deb5a7C400482E9122C`](https://etherscan.io/address/0xa21d2E301D50AfF797143deb5a7C400482E9122C) and codehash `0xb3377dba77dfd8bce7c272e7c4c445ab48b3d0ec3fd0a52f512a39974f059a0f` will be whitelisted in `GROVE_STARGUARD`.

#### Grove Proxy Spell Contents

##### [Ethereum] Onboard the Diamond PAU Controller on the New Grove Allocator Instance

- **Authorization**: [Governance Poll ID 1638](https://vote.sky.money/polling/QmdXjfm6)
- **Proposal**: [July 2, 2026 Proposed Changes to Grove for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-grove-for-upcoming-spell/27976)

If this executive proposal passes, then the Diamond PAU Controller will be onboarded on the new Grove allocator instance.

##### [Ethereum] Onboard the Tokenized Treasury Instances (Basin: JTRSY + BUIDL)

- **Authorization**: [Governance Poll ID 1638](https://vote.sky.money/polling/QmdXjfm6)
- **Proposal**: [July 2, 2026 Proposed Changes to Grove for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-grove-for-upcoming-spell/27976)

If this executive proposal passes, then the tokenized treasury instances for Basin: JTRSY and BUIDL will be onboarded.

##### [Ethereum] Swap USDC to USDS in Grove SubProxy

- **Authorization**: [Sky Atlas](https://sky-atlas.io/#aa16daa3-ee62-49eb-851e-cb0708670144)
- **Proposal**: [July 2, 2026 Proposed Changes to Grove for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-grove-for-upcoming-spell/27976)

If this executive proposal passes, then USDC will be swapped to USDS in the Grove SubProxy.

##### [Ethereum] Treasury Distribution - 800,000 USDS to the Grove Foundation Multisig

- **Authorization**: [Governance Poll ID 1638](https://vote.sky.money/polling/QmdXjfm6)
- **Proposal**: [July 2, 2026 Proposed Changes to Grove for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-grove-for-upcoming-spell/27976)

If this executive proposal passes, then **800,000 USDS** will be transferred to the Grove Foundation Multisig.

### Skybase Proxy Spell

If this executive proposal passes, then a Skybase proxy spell with address [`0xd3e4e16ED515Be794fd181D7d2cEB0447A6f2cb5`](https://etherscan.io/address/0xd3e4e16ED515Be794fd181D7d2cEB0447A6f2cb5) and codehash `0x09c387eed3e4373a4cc91fc28686e103cfc704335279f65f2f7308f474c002d9` will be whitelisted in `SKYBASE_STARGUARD`.

#### Skybase Proxy Spell Contents

##### [Ethereum] Transfer 700,000 USDS from the Skybase SubProxy to the Skybase Foundation Operational Multisig

- **Authorization**: [Governance Poll ID 1638](https://vote.sky.money/polling/QmdXjfm6)
- **Proposal**: [July 2, 2026 Proposed Changes to Skybase for Upcoming Spell](https://forum.skyeco.com/t/july-2-2026-proposed-changes-to-skybase-for-upcoming-spell/27973)

If this executive proposal passes, then **700,000 USDS** will be transferred from the Skybase SubProxy to the Skybase Foundation Operational Multisig.

## Review

Community debate on this executive proposal can be found on the Sky [Governance forum](https://forum.skyeco.com/). Please review any linked threads to inform your position before voting.

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com/). The [Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar) also shows upcoming votes and votes that are currently active.

To participate in voting, please follow the [Voting Guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance).
