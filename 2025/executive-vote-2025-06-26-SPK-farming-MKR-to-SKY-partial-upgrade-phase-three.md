---
title: Template - [Executive Vote] SPK Farming Initialization, Partial Phase 3 MKR-to-SKY Migration, Smart Burn Engine Parameter Updates, ALLOCATOR-BLOOM-A Maximum Debt Ceiling Increase, Spark USDS Transfer, Launch Project Funding, DAO Resolution, Delegate Compensation for May 2025, Atlas Core Development Payments for June 2025, Spark Proxy Spell - June 26, 2025
summary: $summary
date: 2025-06-25T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] SPK Farming Initialization, Partial Phase 3 MKR-to-SKY Migration, Smart Burn Engine Parameter Updates, ALLOCATOR-BLOOM-A Maximum Debt Ceiling Increase, Spark USDS Transfer, Launch Project Funding, DAO Resolution, Delegate Compensation for May 2025, Atlas Core Development Payments for June 2025, Spark Proxy Spell - June 26, 2025

The Governance Facilitators, Dewiz, and Sidestream have placed an executive proposal into the voting system. SKY holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- A new DssVestTransferrable contract for SPK tokens will be deployed.
- SPK farms for USDS and SKY stakers will be initialized.
- A subset of actions relating to phase 3 of the MKR-to-SKY upgrade process will be taken:
	- MKR held in the PauseProxy contract will be converted to SKY.
	- The legacy MKR-to-SKY converter will be disabled.
	- Excess SKY tokens in the MKR-to-SKY converter will be burned to offset tokens minted through the legacy converter.
	- A proportion of SKY tokens held in the PauseProxy will be burned to offset minted SKY tokens.
- Smart Burn Engine parameters will be updated.
- The ALLOCATOR-BLOOM-A Maximum Debt Ceiling (`line`) will be increased.
- **20.6 million USDS** will be transferred to the Spark SubProxy.
- **8.4 million SKY** will be transferred to the Launch Project.
- A DAO Resolution with the hash bafkreidm3bqfiwv224m6w4zuabsiwqruy22sjfaxfvgx4kgcnu3wndxmva will be approved.
- A total of **20,443 USDS** will be distributed as Aligned Delegate compensation for May 2025.
- A total of **77,584 USDS** and **618,000 SKY** will be distributed as Atlas Core Development payments for June 2025.
- A Spark Proxy Spell with the address [0x74e1ba852C864d689562b5977EedCB127fDE0C9F](https://etherscan.io/address/0x74e1ba852C864d689562b5977EedCB127fDE0C9F) will be executed.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.powerhouse.io/#A.1.8.2.1_Pause_Delay-a98b8227-95f6-4711-9d8d-f52cbc6ad2d0|0db30758e055). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**24 hours**](https://sky-atlas.powerhouse.io/#A.1.8.2.1.2_Pause_Delay_Current_Value-09d2514b-3169-4755-a654-2c774456980d|0db30758e055d2d0).

This executive proposal **has its earliest execution date set to June 30, 2025 at 14:00 UTC**. This means that it cannot be executed before that date.

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**. 

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### SPK Token Farming Initialization

- **Authorization**: [Atlas entry](https://sky-atlas.powerhouse.io/A.2.9.1.2.2.1.2.2.2_Spark_Token_Reward_Distribution_Schedule/1fef2ff0-8d73-809d-ac41-eb9753c05d41|9e1f80092582d59891b002d4366698bb), [Governance Poll](https://vote.sky.money/polling/QmXpG84B)
- **Proposal**: [Technical Scope](https://forum.sky.money/t/technical-scope-of-spk-farms/26703), [Atlas Edit Proposal](https://forum.sky.money/t/atlas-edit-weekly-cycle-proposal-week-of-2025-05-26/26454)

If this executive proposal passes, then the following actions required to implement SPK farming will be taken.

#### Pre-Deployed Contracts

##### SPK Vesting Contract Deployment

In order to stream SPK tokens from the PauseProxy to the farming contracts, a new [DssVestTransferrable](https://github.com/sky-ecosystem/dss-vest/blob/41728f0361418ff4831d0987c2b8aadffbf2f539/src/DssVest.sol) contract for SPK vesting has been deployed to [0xF9A2002b471f600A5484da5a735a2A053d377078](https://etherscan.io/address/0xF9A2002b471f600A5484da5a735a2A053d377078) with the following constructor parameters:

- `_czar`: [MCD_PAUSE_PROXY](https://etherscan.io/address/0xBE8E3e3618f7474F8cB1d074A26afFef007E98FB).
- `_gem`: [SPK Token](https://etherscan.io/token/0xC20059E0317De91738D13AF027DfC4a50781b066).

##### USDS -> SPK Farm

A new [StakingRewards](https://github.com/makerdao/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/src/synthetix/StakingRewards.sol) contract to permit farming of SPK tokens with USDS tokens has been deployed to [0x173e314C7635B45322cd8Cb14f44b312e079F3af](https://etherscan.io/address/0x173e314C7635B45322cd8Cb14f44b312e079F3af) with the following constructor parameters:

- `_owner`: [MCD_PAUSE_PROXY](https://etherscan.io/address/0xBE8E3e3618f7474F8cB1d074A26afFef007E98FB).
- `_rewardsDistribution`: address(0).
- `_rewardsToken`: [SPK](https://etherscan.io/token/0xC20059E0317De91738D13AF027DfC4a50781b066).
- `_stakingToken`: [USDS](https://etherscan.io/token/0xdC035D45d973E3EC169d2276DDab16f1e407384F).

A new [VestedRewardsDistribution](https://github.com/makerdao/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/src/VestedRewardsDistribution.sol) contract to permit farming of SPK tokens with USDS tokens has been deployed to [0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c](https://etherscan.io/address/0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c) with the following constructor parameters:

- `_dssVest`: The newly created SPK vesting contract deployed at [0xF9A2002b471f600A5484da5a735a2A053d377078](https://etherscan.io/address/0xF9A2002b471f600A5484da5a735a2A053d377078).
- `_stakingRewards`: The newly created staking rewards contract deployed at [0x173e314C7635B45322cd8Cb14f44b312e079F3af](https://etherscan.io/address/0x173e314C7635B45322cd8Cb14f44b312e079F3af).

##### LSSKY -> SPK Farm

A new [StakingRewards](https://github.com/makerdao/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/src/synthetix/StakingRewards.sol) contract to permit farming of SPK tokens with USDS tokens has been deployed to [0x99cBC0e4E6427F6939536eD24d1275B95ff77404](https://etherscan.io/address/0x99cBC0e4E6427F6939536eD24d1275B95ff77404) with the following constructor parameters:

- `_owner`: [MCD_PAUSE_PROXY](https://etherscan.io/address/0xBE8E3e3618f7474F8cB1d074A26afFef007E98FB).
- `_rewardsDistribution`: address(0).
- `_rewardsToken`: [SPK](https://etherscan.io/token/0xC20059E0317De91738D13AF027DfC4a50781b066).
- `_stakingToken`: [LSSKY](https://etherscan.io/token/0xf9a9cfd3229e985b91f99bc866d42938044ffa1c).

A new [VestedRewardsDistribution](https://github.com/makerdao/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/src/VestedRewardsDistribution.sol) contract to permit farming of SPK tokens with USDS tokens has been deployed to [0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e](https://etherscan.io/address/0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e) with the following constructor parameters:

- `_dssVest`: The newly created SPK vesting contract deployed at [0xF9A2002b471f600A5484da5a735a2A053d377078](https://etherscan.io/address/0xF9A2002b471f600A5484da5a735a2A053d377078).
- `_stakingRewards`: The newly created staking rewards contract deployed at [0x99cBC0e4E6427F6939536eD24d1275B95ff77404](https://etherscan.io/address/0x99cBC0e4E6427F6939536eD24d1275B95ff77404).

#### Contract Initialization

##### SPK Vest Initializaion

If this executive proposal passes the SPK vesting contract will be initialized by performing the following actions:

- The vesting contract will be approved to spend SPK held in the PauseProxy with the following parameters:
	- `spender`: [0xF9A2002b471f600A5484da5a735a2A053d377078](https://etherscan.io/address/0xF9A2002b471f600A5484da5a735a2A053d377078)
	- `amount`: **3_250_000_000 * WAD** (This is the total amount of SPK tokens being streamed by vests created in this spell)
- The `cap` of the vesting contract will be set to **2_502_500_000 * WAD / 730 days** (This value is the maximum amount of SPK that can be vested per second per vesting stream. It should be greater than or equal to the largest vesting stream rate. In this spell we are adding the conventional 10% buffer to avoid any issues.)
- Add MCD_VEST_SKY_TREASURY to the [Chainlog](https://chainlog.sky.money/) with the value [0xF9A2002b471f600A5484da5a735a2A053d377078](https://etherscan.io/address/0xF9A2002b471f600A5484da5a735a2A053d377078).
- Add SPK to the [Chainlog](https://chainlog.sky.money/) with the value [0xC20059E0317De91738D13AF027DfC4a50781b066)](https://etherscan.io/token/0xC20059E0317De91738D13AF027DfC4a50781b066).

##### USDS -> SPK Farm Initialization

If this executive proposal passes the USDS -> SPK farm will be initialized through the following actions:

###### Create the Vesting Stream

Call [VestInit.create()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/script/dependencies/VestInit.sol#L28-L39) with the following parameters:

- `vest`: [0xF9A2002b471f600A5484da5a735a2A053d377078](https://etherscan.io/address/0xF9A2002b471f600A5484da5a735a2A053d377078).
- `p.usr`: [0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c](https://etherscan.io/address/0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c).
- `p.tot`: 2_275_000_000 * WAD.
- `p.bgn`: block.timestamp - 7 days.
- `p.tau`: 730 days.
- `p.eta`: 0.
- `restricted`: true (VestInit.create() restricts the stream by default).

This will create a vesting stream vesting 2.275 billion SKY over 2 years to the relevant VestedRewardsDistribution contract.

###### Initialize the StakingRewards Contract

Call [StakingRewardsInit.init()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/script/dependencies/StakingRewardsInit.sol#L27-L29) with the following parameters:

- `rewards`: [0x173e314C7635B45322cd8Cb14f44b312e079F3af](https://etherscan.io/address/0x173e314C7635B45322cd8Cb14f44b312e079F3af).
- `p.dist`: [0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c](https://etherscan.io/address/0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c).
- `duration`: 7 days (this is the default value for StakingRewards contracts).

###### Initialize the VestedRewardsDistribution Contract

Call [VestedRewardsDistributionInit.init()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/script/dependencies/VestedRewardsDistributionInit.sol#L23-L25) with the following parameters:

- `dist`: [0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c](https://etherscan.io/address/0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c).
- `p.vestId`: vestIdUsdsSpk (the ID of the vesting stream created for this farm).

###### Call distribute() on The VestedRewardsDistribution Contract

[distribute()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/src/VestedRewardsDistribution.sol#L152-L165) will be called on the new VestedRewardsDistribution contract.

###### Add the VestedRewardsDistribution Contract to the Keeper Job

The new VestedRewardsDistribution contract will be added to the keeper job by calling set() on [CRON_REWARDS_DIST_JOB](https://etherscan.io/address/0x6464c34a02dd155dd0c630ce233dd6e21c24f9a5) with the following parameters:

- `dist`: [0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c](https://etherscan.io/address/0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c).
- `period`: 7 days - 1 hours (the default farm rewards epoch duration minus 1 hour is used to avoid disruption in the rewards distribution schedule in cases where the chain is too busy or the keepers fail to execute the jobs on time).

###### Add New Contracts to the Chainlog

The new VestedRewardsDistribution and StakingRewards contracts will be added to the [Chainlog](https://chainlog.sky.money/) with the following key-value pairs:

- REWARDS_USDS_SPK: [0x173e314C7635B45322cd8Cb14f44b312e079F3af](https://etherscan.io/address/0x173e314C7635B45322cd8Cb14f44b312e079F3af).
- REWARDS_DIST_USDS_SPK: [0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c](https://etherscan.io/address/0x3959e23A63CA7ac12D658bb44F90cb1f7Ee4C02c).

##### LSSKY -> SPK Farm Initialization

If this executive proposal passes the LSSKY -> SPK farm will be initialized through the following actions:

###### Create the Vesting Stream

Call [VestInit.create()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/script/dependencies/VestInit.sol#L28-L39) with the following parameters:

- `vest`: [0xF9A2002b471f600A5484da5a735a2A053d377078](https://etherscan.io/address/0xF9A2002b471f600A5484da5a735a2A053d377078).
- `p.usr`: [0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e](https://etherscan.io/address/0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e).
- `p.tot`: 975_000_000 * WAD.
- `p.bgn`: block.timestamp - 7 days.
- `p.tau`: 730 days.
- `p.eta`: 0.
- `restricted`: true (VestInit.create() restricts the stream by default).

This will create a vesting stream vesting 975 million SKY over 2 years to the relevant VestedRewardsDistribution contract.

###### Initialize the StakingRewards Contract

Call [StakingRewardsInit.init()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/script/dependencies/StakingRewardsInit.sol#L27-L29) with the following parameters:

- `rewards`: [0x99cBC0e4E6427F6939536eD24d1275B95ff77404](https://etherscan.io/address/0x99cBC0e4E6427F6939536eD24d1275B95ff77404).
- `p.dist`: [0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e](https://etherscan.io/address/0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e).
- `duration`: 7 days (this is the default value for StakingRewards contracts).

###### Initialize the VestedRewardsDistribution Contract

Call [VestedRewardsDistributionInit.init()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/script/dependencies/VestedRewardsDistributionInit.sol#L23-L25) with the following parameters:

- `dist`: [0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e](https://etherscan.io/address/0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e).
- `p.vestId`: vestIdLsskySpk (the ID of the vesting stream created for this farm).

###### Call distribute() on The VestedRewardsDistribution Contract

[distribute()](https://github.com/sky-ecosystem/endgame-toolkit/blob/5bf4b1771b99f5f8758fd40a4ac567f797b5405b/src/VestedRewardsDistribution.sol#L152-L165) will be called on the new VestedRewardsDistribution contract.

###### Add the VestedRewardsDistribution Contract to the Keeper Job

The new VestedRewardsDistribution contract will be added to the keeper job by calling set() on [CRON_REWARDS_DIST_JOB](https://etherscan.io/address/0x6464c34a02dd155dd0c630ce233dd6e21c24f9a5) with the following parameters:

- `dist`: [0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e](https://etherscan.io/address/0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e).
- `period`: 7 days - 1 hours (the default farm rewards epoch duration minus 1 hour is used to avoid disruption in the rewards distribution schedule in cases where the chain is too busy or the keepers fail to execute the jobs on time).

###### Add LSSKY -> SPK farm to the Lockstake Engine

The new StakingRewards contract will be added as a farm to the Lockstake Engine by calling [addFarm()](https://github.com/sky-ecosystem/lockstake/blob/master/src/LockstakeEngine.sol#L198-L201) with the following parameter:

- `farm`: [0x99cBC0e4E6427F6939536eD24d1275B95ff77404](https://etherscan.io/address/0x99cBC0e4E6427F6939536eD24d1275B95ff77404).

###### Add New Contracts to the Chainlog

The new VestedRewardsDistribution and StakingRewards contracts will be added to the [Chainlog](https://chainlog.sky.money/) with the following key-value pairs:

- REWARDS_LSSKY_SPK: [0x99cBC0e4E6427F6939536eD24d1275B95ff77404](https://etherscan.io/address/0x99cBC0e4E6427F6939536eD24d1275B95ff77404).
- REWARDS_DIST_LSSKY_SPK: [0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e](https://etherscan.io/address/0xa3Ee378BdD0b7DD403cEd3a0A65B2B389A2eaB7e).

### $executive_entry_2

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_2_implications.

### $executive_entry_3

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
