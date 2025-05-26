---
title: Template - [Executive Vote] MKR Upgrade Phase Two, Switch SKY Token Rewards Vesting Stream Source, Init Unichain and Optimism Native Bridges, Deactivate SparkLend DDM, Transfer Ownership of SPK Token to SPK Company Multisig, Increase ALLOCATOR-SPARK-A Maximum Debt Ceiling, Launch Project Funding, Delegate Compensation for April 2025, Atlas Core Development USDS and SKY Payments for May 2025, Spark Proxy Spell - May 29, 2025
summary: Phase Two parameter changes for MKR to SKY Upgrade, Change source of SKY For USDS Rewards to the Pause Proxy, Initialization parameters for Native Bridges on Unichain and Optimism, SparkLend Direct Deposit Module deactivation and removal from autoline, Transfer Ownership of SPK Token to SPK Company Multisig, Increase ALLOCATOR-SPARK-A Maximum Debt Ceiling, Transfer Launch Project Fundind, Distribute Delegate Compensation for April 2025, Distribute Atlas COre Development USDS and SKY payments for May 2025, Execute a Spark Proxy Spell.
date: 2025-05-29T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] MKR Upgrade Phase Two, Switch SKY Token Rewards Vesting Stream Source, Init Unichain and Optimism Native Bridges, Deactivate SparkLend DDM, Transfer Ownership of SPK Token to SPK Company Multisig, Increase ALLOCATOR-SPARK-A Maximum Debt Ceiling, Launch Project Funding, Delegate Compensation for April 2025, Atlas Core Development USDS and SKY Payments for May 2025, Spark Proxy Spell - May 29, 2025 - May 29, 2025

The Governance Facilitators, Dewiz, and Sidestream have placed an executive proposal into the voting system. SKY Holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- Multiple parameter updates for MKR to SKY Upgrade Phase Two.
- The source for Sky Token Rewards (SKY to USDS) will be changed to the Pause Proxy.
- Unichain Native Bridge will be launched with initial listed parameters.
- Optimism Native Bridge will be launched with initial listed parameters.
- The SparkLend Direct Deposit Module (DDM) Debt Ceiling will be deactivated.
- Ownership of SPK Token will be transfered to the SPK Company Multisig.
- ALLOCATOR-SPARK-A Maximum Debt Ceiling (`line`) will be increased.
- **5,000,000 USDS** will be distributed to the Launch Project at [0x3C5142F28567E6a0F172fd0BaaF1f2847f49D02F](https://etherscan.io/address/0x3C5142F28567E6a0F172fd0BaaF1f2847f49D02F).
- A total of **26,267 USDS** will be distributed as Aligned Delegate compensation for April 2025.
- A total of **77,584 USDS** and **618,000 SKY** will be distributed as Atlas Core Development payments.
- A Spark proxy spell will be executed.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.powerhouse.io/#A.1.8.2.1_Pause_Delay-a98b8227-95f6-4711-9d8d-f52cbc6ad2d0|0db30758e055). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**48 hours**](https://sky-atlas.powerhouse.io/#A.1.8.2.1.2_Pause_Delay_Current_Value-09d2514b-3169-4755-a654-2c774456980d|0db30758e055d2d0).

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**. 

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### MKR to SKY Upgrade Phase Two

- **Authorization**: [Atlas](https://sky-atlas.powerhouse.io/A.4.1.2.1.2_MKR_To_SKY_Upgrade_Phase_Two/1f1f2ff0-8d73-80ee-81e9-f508c45f90ed|b341f4c0b83472dc), (Governance Poll 1245](https://vote.makerdao.com/polling/QmcZNZg3)  
- **Proposal**: [Forum Post](https://forum.sky.money/t/atlas-edit-weekly-cycle-proposal-week-of-may-5-2025/26319)

If this executive proposal passes, then the following set of changes will take place to complete Phase Two of the MKR to SKY Upgrade.

#### Activate USDS Rewards on the LSEV2-SKY-A Contract

- Reduce splitter.burn by 50 percentage points from 100% to **50%**.

#### LSEV2-SKY-A AutoLine Addition

- Add LSEV2-SKY-A to the AutoLine.
- Set `line` to **50,000,000 USDS**.
- Set `gap` to **25,000,000 USDS**.
- Set ttl to **86,400 seconds**.

#### Adjust GSM Pause Delay

- Reduce GSM Pause Delay by 24 hours from 48 hours to **24 hours**.

#### Revoke Migrator Authority Over Vat Contract

- Revoke LOCKSTAKE_MIGRATOR's authority over the vat.

### Change Source of Sky Token Rewards (SKY to USDS) to the Pause Proxy.

- **Authorization**: [Ecosystem Approval]($TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/proposed-housekeeping-item-upcoming-executive-spell-2025-05-29/26448)

If this executive proposal passes, then a new stream will be initialized for Sky Token Rewards. This stream will be adjusted to match SSR by changing the rewards distribution rate. The new stream additionally changes the source for the SKY to the PauseProxy. These changes are achieved by executing the following actions:

- `yank` MCD_VEST_SKY stream ID 2.
- Claim the remaining tokens from the old DssVest by calling VestedRewardsDistribution.distribute() on REWARDS_DIST_USDS_SKY
- Set cap on MCD_VEST_SKY_TREASURY to `151,250,000 * WAD / 182 days`.
- Increase sky.approve(MCD_VEST_SKY_TREASURY, ...) by 137,500,000 SKY to account for new vesting stream.
- Remove old REWARDS_USDS_SKY_DIST from the keeper job by calling `CRON_REWARDS_DIST_JOB.rem()` with the current REWARDS_USDS_SKY_DIST. 
- Update chainlog value for REWARDS_USDS_SKY_DIST to the new VestedRewardsDistribution contract at [0xC8d67Fcf101d3f89D0e1F3a2857485A84072a63F](https://etherscan.io/address/0xC8d67Fcf101d3f89D0e1F3a2857485A84072a63F).
- Add new REWARDS_USDS_SKY_DIST to the keeper job by calling `CRON_REWARDS_DIST_JOB.set()` with the new REWARDS_USDS_SKY_DIST.
- Deploy new MCD_VEST_SKY_TREASURY stream with the following parameters: usr(REWARDS_USDS_SKY_DIST), tot(137,500,000 SKY), bgn(block.timestamp), tau(182 days), cliff: none, manager, none.
- Restrict the new stream, res: 1.
- File the id of the newly created stream to the new REWARDS_USDS_SKY_DIST contract.

### Init Unichain Native Bridge

- **Authorization**: [Governance Poll 1253](https://vote.makerdao.com/polling/QmXjeJtw)
- **Proposal**: [Forum Post](https://forum.sky.money/t/may-29-2025-proposed-changes-to-spark-for-upcoming-spell/26372)

If this executive proposal passes, then the Unichain Token Bridge for USDS and sUSDS will be initialized by calling TokenBridgeInit.initBridges using the following parameters.

#### Set l1BridgeInstance 

- Set parameter l1BridgeInstance.govRelay: (L1GovernanceRelay: 0xb383070Cf9F4f01C3a2cfD0ef6da4BC057b429b7)
- Set parameter l1BridgeInstance.escrow: (Escrow: 0x1196F688C585D3E5C895Ef8954FFB0dCDAfc566A)
- Set parameter l1BridgeInstance.bridge: (ERC1967Proxy: 0xDF0535a4C96c9Cd8921d8FeC92A7680b281681d2)
- Set parameter l1BridgeInstance.bridgeImp: (L1TokenBridge: 0x8A925ccFd5F7f46332E2D719A916f8b4a643599F)

#### Set l2BridgeInstance (Unichain Network)

- Set parameter l2BridgeInstance.govRelay: (L2GovernanceRelay: 0x3510a7F16F549EcD0Ef018DE0B3c2ad7c742990f)
- Set parameter l2BridgeInstance.bridge: (ERC1967Proxy: 0xa13152006D0216Fe4627a0D3B006087A6a55D752)
- Set parameter l2BridgeInstance.bridgeImp: (L2TokenBridge: 0xd78292C12707CF28E8EB7bf06fA774D1044C2dF5)
- Set parameter l2BridgeInstance.spell: (L2TokenBridgeSpell: 0x32760698c87834c02ED9AFF2d4FC3e16c029B936)

#### Set cfg 

- Set parameter cfg.l1Messenger: (l1messenger 0x9A3D64E386C18Cb1d6d5179a9596A4B5736e98A6)
- Set parameter cfg.l2Messenger: (l2messenger 0x4200000000000000000000000000000000000007)
- Set parameter cfg.l1Tokens: (USDS, SUSDS on mainnet)
- Set parameter cfg.l2Tokens: (USDS: 0x7E10036Acc4B56d4dFCa3b77810356CE52313F9C, sUSDS: 0xA06b10Db9F390990364A3984C04FaDf1c13691b5 on Unichain)
- Set parameter cfg.maxWithdraws: (type(uint256).max for each token)
- Set parameter cfg.minGasLimit: (500,000)
- Set parameter cfg.govRelayCLKey: (chainlog key for govRelay -> UNICHAIN_GOV_RELAY)
- Set parameter cfg.escrowCLKey: (chainlog key for Escrow -> UNICHAIN_ESCROW)
- Set parameter cfg.l1BridgeCLKey: (chainlog key for L1TokenBridge -> UNICHAIN_TOKEN_BRIDGE)
- Set parameter cfg.l1BridgeImpCLKey: (chainlog key for L1TokenBridgeImp -> UNICHAIN_TOKEN_BRIDGE_IMP)

### Init Optimism Native Bridge

- **Authorization**: [Governance Poll 1254](https://vote.makerdao.com/polling/QmNe8Erm)
- **Proposal**: [Forum Post](https://forum.sky.money/t/may-29-2025-proposed-changes-to-spark-for-upcoming-spell/26372)

If this executive proposal passes, then the Optimism Token Bridge for USDS and sUSDS will be initialized by calling TokenBridgeInit.initBridges using the following parameters.

#### Set l1BridgeInstance 

- Set parameter l1BridgeInstance.govRelay: (L1GovernanceRelay: 0x09B354CDA89203BB7B3131CC728dFa06ab09Ae2F)
- Set parameter l1BridgeInstance.escrow: (Escrow: 0x467194771dAe2967Aef3ECbEDD3Bf9a310C76C65)
- Set parameter l1BridgeInstance.bridge: (ERC1967Proxy: 0x3d25B7d486caE1810374d37A48BCf0963c9B8057)
- Set parameter l1BridgeInstance.bridgeImp: (L1TokenBridge: 0xA50adBad34c1e9786979bD44220F8fd46e43A6B0)

#### Set l2BridgeInstance (Optimism Network)

Set parameter l2BridgeInstance.govRelay: (L2GovernanceRelay: 0x10E6593CDda8c58a1d0f14C5164B376352a55f2F)
Set parameter l2BridgeInstance.bridge: (ERC1967Proxy: 0x8F41DBF6b8498561Ce1d73AF16CD9C0d8eE20ba6)
Set parameter l2BridgeInstance.bridgeImp: (L2TokenBridge: 0xc2702C859016db756149716cc4d2B7D7A436CF04)
Set parameter l2BridgeInstance.spell: (L2TokenBridgeSpell: 0x99892216eD34e8FD924A1dBC758ceE61a9109409)

#### Set cfg 

- Set parameter cfg.l1Messenger: (l1messenger: 0x25ace71c97B33Cc4729CF772ae268934F7ab5fA1)
- Set parameter cfg.l2Messenger: (l2messenger: 0x4200000000000000000000000000000000000007)
- Set parameter cfg.l1Tokens: (USDS, SUSDS on mainnet)
- Set parameter cfg.l2Tokens: (USDS: 0x4F13a96EC5C4Cf34e442b46Bbd98a0791F20edC3, sUSDS: 0xb5B2dc7fd34C249F4be7fB1fCea07950784229e0 on Optimism)
- Set parameter cfg.maxWithdraws: (type(uint256).max for each token)
- Set parameter cfg.minGasLimit: (500,000)
- Set parameter cfg.govRelayCLKey: (chainlog key for govRelay -> OPTIMISM_GOV_RELAY)
- Set parameter cfg.escrowCLKey: (chainlog key for Escrow -> OPTIMISM_ESCROW)
- Set parameter cfg.l1BridgeCLKey: (chainlog key for L1TokenBridge -> OPTIMISM_TOKEN_BRIDGE)
- Set parameter cfg.l1BridgeImpCLKey: (chainlog key for L1TokenBridgeImp -> OPTIMISM_TOKEN_BRIDGE_IMP)

### Deactivate SparkLend DDM

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

### Transfer Ownership of SPK Token to SPK Company Multisig

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

### Increase ALLOCATOR-SPARK-A Maximum Debt Ceiling

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

### Launch Project Funding

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

### Atlas Core Development USDS Payments for May 2025

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

### Atlas Core Development SKY Payments for May 2025

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

### Execute Spark Proxy Spell

- **Authorization**: [$link_to_approval]()
- **Proposal**: [$link_to_proposal]()

If this executive proposal passes, then $executive_entry_3_implications.

## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
