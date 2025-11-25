---
title: Template - [Executive Vote] Launch StarGuards, Monthly Settlement Cycle and Treasury Management Function, Whitelist Keel Subproxy, Ranked Delegate Compensation, Atlas Core Development Compensation, Payment to Gnosis, Add OBEX to SP-BEAM, Prime Agent Proxy Spells - November 27, 2025
summary: Launch Starguard for Grove, Keel, and Obex, Monthly Settlement Cycle and Treasury Management Function for October, Whitelist the Keel SubProxy to send cross-chain messages to Solana, Ranked Delegate Compensation for October, Atlas Core Development USDS and SKY payments for November, Gnosis Payment for the difference between the Sky Savings Rate and the Dai Savings Rate on xDai, add ALLOCATOR-OBEX-A to SP-BEAM, whitelist Spark Proxy Spell in Starguard, execute Keel Proxy Spell. 
date: 2025-11-27T00:00:00.000Z
address: "$spell_address"
--- 

# [Executive Proposal] Launch Starguards, Monthly Settlement Cycle and Treasury Management Function for October, Whitelist Keel Subproxy, Ranked Delegate Compensation, Atlas Core Development Compensation, Payment to Gnosis, Add ALLOCATOR-OBEX-A to SP-BEAM, Prime Agent Proxy Spells - November 27, 2025

The  Core Facilitators, Dewiz, and Sidestream have placed an executive proposal into the voting system. SKY holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- StarGaurd modules for Grove, Keel, and Obex will be launched.
- The Monthly Settlement Cycle and Treasury Management Function for October 2025 will be executed.
- The Keel Subproxy will be whitelisted to send cross-chain messages to Solana, as described below.
- A total of **23,479 USDS** will be distributed to six Ranked Delegates as compensation for October 2025.
- A total of **66,584 USDS** and **618,000 SKY** will be distributed as Atlas Core Development compensation for November 2025.
- **1,806,670 USDS** will be transferred to Gnosis at [0x849D52316331967b6fF1198e5E32A0eB168D039d](https://etherscan.io/address/0x849D52316331967b6fF1198e5E32A0eB168D039d).
- ALLOCATOR-OBEX-A will be added to SP-BEAM, as described below.
- A proxy spell for Spark will be whitelisted in the Spark StarGuard.
- A proxy spell for Keel will be executed.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.io/#A.1.9.3.1). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**24 hours**](https://sky-atlas.io/#A.1.9.3.1.2).

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**.

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### Launch Grove StarGuard

- **Authorization**: [$link_to_approval](TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/technical-scope-of-the-starguard-launches-for-grove-keel-and-obex/27441)

If this executive proposal passes, then StarGaurd for Grove will be launched, to be used to whitelist future Grove Proxy Spells.

### Launch Keel StarGuard

- **Authorization**: [$link_to_approval](TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/technical-scope-of-the-starguard-launches-for-grove-keel-and-obex/27441)

If this executive proposal passes, then StarGaurd for Keel will be launched, to be used to whitelist future Keel Proxy Spells.

### Launch Obex StarGuard

- **Authorization**: [$link_to_approval](TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/technical-scope-of-the-starguard-launches-for-grove-keel-and-obex/27441)

If this executive proposal passes, then StarGaurd for Obex will be launched, to be used to whitelist future Obex Proxy Spells.

### Monthly Settlement Cycle and Treasury Management Function for October

- **Authorization**: [A.2.5](https://sky-atlas.io/#A.2.5)
- **Proposal**: [Forum Post](https://forum.sky.money/t/msc-3-settlemnt-summary-october-2025-initial-calculation/27397/3)

If this executive proposal passes, then the following steps to execute the September 2025 Monthly Settlement Cycle will be taken.

#### Spark

- Mint **16,332,535 USDS debt** in ALLOCATOR-SPARK-A and transfer the amount to the Surplus Buffer.
- Transfer **4,642,240 USDS** from the Surplus Buffer to the Spark SubProxy at [0x3300f198988e4C9C63F75dF86De36421f06af8c4](https://etherscan.io/address/0x3300f198988e4C9C63F75dF86De36421f06af8c4).

#### Grove

- Mint **4,196,768 USDS debt** in ALLOCATOR-BLOOM-A and transfer the amount to the Surplus Buffer.

#### Treasury Management 

- Transfer **3,177,413 USDS** to the Core Council Buffer Multisig at [0x210CFcF53d1f9648C1c4dcaEE677f0Cb06914364](https://etherscan.io/address/0x210CFcF53d1f9648C1c4dcaEE677f0Cb06914364).
- Transfer **158,871 USDS** to the Aligned Delegates Buffer Multisig at [0x37FC5d447c8c54326C62b697f674c93eaD2A93A3](https://etherscan.io/address/0x37FC5d447c8c54326C62b697f674c93eaD2A93A3)

### Whitelist the Keel SubProxy to Send Cross-Chain Messages to Solana

- **Authorization**: [Governance Poll 1606](https://vote.sky.money/polling/QmdomJ7o)
- **Proposal**: [Forum Post 1](https://forum.sky.money/t/atlas-edit-weekly-cycle-proposal-week-of-2025-11-17/27421), [2](https://forum.sky.money/t/executive-inclusion-whitelisting-the-keel-subproxy-to-send-cross-chain-messages-to-solana/27447)

If this executive proposal passes, then the Keel Subproxy will be whitelisted to send cross-chain messages to Solana. This will allow the Keel SubProxy on mainnet to control the Solana ALM Controller and upgrade it in future, if required. This is achieved through the following calls:

- Call `setCanCallTarget` on [LZ_GOV_SENDER](https://etherscan.io/address/0x27FC1DD771817b53bE48Dc28789533BEa53C9CCA) with the following parameters:
  - _srcSender: KEEL_SUBPROXY
  - _dstEID: SOL_EID defined by LayerZero
  - _dstTarget: ALM1JSnEhc5PkNecbSZotgprBuJujL5objTbwGtpTgTd
  - _canCall: true
- Call `setCanCallTarget` on [LZ_GOV_SENDER](https://etherscan.io/address/0x27FC1DD771817b53bE48Dc28789533BEa53C9CCA) with the following parameters:
  - _srcSender: KEEL_SUBPROXY
  - _dstEID: SOL_EID defined by LayerZero
  - _dstTarget: BPFLoaderUpgradeab1e11111111111111111111111
  - _canCall: true

### Delegate Compensation for October 2025

- **Authorization**: [A.1.5](https://sky-atlas.io/#A.1.5)
- **Proposal**: [Forum Post](https://forum.sky.money/t/october-2025-ranked-delegate-compensation/27412)

If this executive proposal passes, then a total of **23,479 USDS** will be distributed to six Ranked Delegates as follows:

| Delegate    | Amount (USDS) | Address                                                                                                               |
|-------------|---------------|-----------------------------------------------------------------------------------------------------------------------|
| AegisD      | 4,000         | [0x78C180CF113Fe4845C325f44648b6567BC79d6E0](https://etherscan.io/address/0x78C180CF113Fe4845C325f44648b6567BC79d6E0) |
| BLUE        | 4,000         | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |
| Bonapublica | 4,000         | [0x167c1a762B08D7e78dbF8f24e5C3f1Ab415021D3](https://etherscan.io/address/0x167c1a762B08D7e78dbF8f24e5C3f1Ab415021D3) |
| Cloaky      | 4,000         | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |
| Sky Staking | 3,783         | [0x05c73AE49fF0ec654496bF4008d73274a919cB5C](https://etherscan.io/address/0x05c73AE49fF0ec654496bF4008d73274a919cB5C) |
| Tango | 3,696         | [0xB2B86A130B1EC101e4Aed9a88502E08995760307](https://etherscan.io/address/0xB2B86A130B1EC101e4Aed9a88502E08995760307) |

### Atlas Core Development Payments for November 2025

- **Authorization**: [A.2.2.1.1](https://sky-atlas.io/#A.2.2.1.1)
- **Proposal**: [Forum Post](https://forum.sky.money/t/atlas-core-development-payment-requests-november-2025/27402)

If this executive proposal passes, then a total of **66,584 USDS** and **618,000 SKY** will be distributed as Atlas Core Development payments for November 2025 as follows.

#### USDS Payments

| Recipient | Amount (USDS) | Address                                                                                                               |
|-----------|--------------:|-----------------------------------------------------------------------------------------------------------------------|
| BLUE      | 50,167        | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |
| Cloaky    | 16,417        | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |

#### SKY Payments

| Recipient | Amount (SKY) | Address                                                                                                               |
|-----------|-------------:|-----------------------------------------------------------------------------------------------------------------------|
| BLUE      | 330,000      | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |
| Cloaky    | 288,000      | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |

### Payment to Gnosis

- **Authorization**: [A.4.1.1.1.1](https://sky-atlas.io/#A.4.1.1.1.1)
- **Proposal**: [Forum Post](https://forum.sky.money/t/atlas-edit-weekly-cycle-proposal-week-of-2025-11-10/27400)

If this executive proposal passes, then the following transfer will be made for the difference between the Sky Savings Rate and the Dai Savings Rate on xDai:

-Transfer **1,806,670 USDS** to Gnosis at [0x849D52316331967b6fF1198e5E32A0eB168D039d](https://etherscan.io/address/0x849D52316331967b6fF1198e5E32A0eB168D039d).

### Add ALLOCATOR-OBEX-A to SP-BEAM

- **Authorization**: [A.3.7.1.2.3](https://sky-atlas.io/#A.3.7.1.2.3)
- **Proposal**: [Forum Post](https://forum.sky.money/t/executive-inclusion-add-allocator-obex-a-to-the-sp-beam/27442)

If this executive proposal passes, then ALLOCATOR-OBEX-A will be added to the SP-BEAM with the following parameters:

- [max](https://sky-atlas.io/#A.3.7.1.2.1.2): 3,000 basis points
- [min](https://sky-atlas.io/#A.3.7.1.2.1.1): 0 basis points
- [step](https://sky-atlas.io/#A.3.7.1.2.1.3): 400 basis points
- 
### Prime Agent Proxy Spells

If this executive proposal passes, then a Spark Proxy Spell at [0x2C9E477313EC440fe4Ab6C98529da2793e6890F2](https://etherscan.io/address/0x2C9E477313EC440fe4Ab6C98529da2793e6890F2) with the codehash 0xfad4d50e95e43a5d172619770dac42160a77258693d15be09343c5b29f88c521 will be whitelisted in the Spark StarGuard.

If this executive proposal passes, then a Keel Proxy Spell at [0x2395AF361CdF86d348B07E109E710943AFDb23aa](https://etherscan.io/address/0x2395AF361CdF86d348B07E109E710943AFDb23aa) will be executed.

#### Spark

##### [Mainnet] Arkis Funding

- **Authorization**: [Snapshot Poll](https://snapshot.box/#/s:sparkfi.eth/proposal/0x9dd06e68b3b109b616cc7cf7af7f1cf78ed9408312bfb9fe43764a3b3dba563a)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-proposed-changes-to-spark-for-upcoming-spell/27418)

A transfer of **4 million USDS** will be made to [0x92e4629a4510AF5819d7D1601464C233599fF5ec](https://etherscan.io/address/0x92e4629a4510AF5819d7D1601464C233599fF5ec) to fund the Arkis Strategic Investment. 

##### [Mainnet] Onboard B2C2 Penny

- **Authorization**: [Governance Poll 1589](https://vote.sky.money/polling/QmTNrfXk)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-proposed-changes-to-spark-for-upcoming-spell/27418)

B2C2 Penny will be onboarded to provide OTC services for the following tokens with the listed [rate limits](https://sky-atlas.powerhouse.io/A.2.3.9.1.1.1.1.2_Rate_Limits/264f2ff0-8d73-8050-892b-e4a0ed9828dc|9e1ff936a6cb63b1903ca2d845de):

* USDC transferAsset
  * Recipient address: tbd upon completion of B2C2 onboarding, will be provided before inclusion in executive spell
  * maxAmount: **1 million USDC**
  * slope: **20 million USDC per day**
* USDT transferAsset
  * Recipient address: tbd upon completion of B2C2 onboarding, will be provided before inclusion in executive spell
  * maxAmount: **1 million USDT**
  * slope: **20 million USDT per day**
* PYUSD transferAsset
  * Recipient address: tbd upon completion of B2C2 onboarding, will be provided before inclusion in executive spell
  * maxAmount: **1 million PYUSD**
  * slope: **20 million PYUSD per day**

##### [Mainnet] Foundation Grant

- **Authorization**: [A.2.9.2.2.2.5.1](https://sky-atlas.io/#A.2.9.2.2.2.5.5.1)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-proposed-changes-to-spark-for-upcoming-spell/27418)

Spark will transfer funding for the December Spark Foundation Grant to the Spark Foundation:

- Payment Amount: **1.1 million USDS**
- Payment Source: **Spark SubProxy**
- Payment Receipt Address: [0x92e4629a4510AF5819d7D1601464C233599fF5ec](https://etherscan.io/address/0x92e4629a4510AF5819d7D1601464C233599fF5ec) (Spark Foundation)

##### [Mainnet] Claim SparkLend Reserves

- **Authorization**: [A.6.1.1.1.2.6.1.2.1.2.3](https://sky-atlas.io/#A.6.1.1.1.2.6.1.2.1.2.3)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-proposed-changes-to-spark-for-upcoming-spell/27418)

All accrued reserves for SparkLend USDS and SparkLend DAI will be claimed.

##### Upgrade ALM Controller to v1.8

- **Authorization**: [Snapshot Poll](https://snapshot.box/#/s:sparkfi.eth/proposal/0xcaafeb100a8ec75ae1e1e9d4059f7d2ec2db31aa55a09be2ec2c7467e0f10799)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-proposed-changes-to-spark-for-upcoming-spell/27418)

The ALM Controller will be upgraded to v1.8 on Mainnet, Base, Arbitrum, Optimism, Unichain, and Avalanche.

#### Keel

##### [Mainnet] Adjust ALM Controller parameters to prepare for Solana launch

- **Authorization**: [Governance Poll 1606](https://vote.sky.money/polling/QmdomJ7o)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-prime-technical-scope-parameter-change-for-upcoming-spell/27406)

Rate limits for various parameters will be updated for the Solana launch, as described in this [forum post](https://forum.sky.money/t/november-27-2025-prime-technical-scope-parameter-change-for-upcoming-spell/27406).

##### [Solana] Launch Allocation System on Solana

- **Authorization**: [Governance Poll 1606](https://vote.sky.money/polling/QmdomJ7o)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-prime-technical-scope-parameter-change-for-upcoming-spell/27406)

The Allocation System for Keel will be launched on Solana, allowing for the deployment of USDS allocations on Solana.

##### [Solana] Onboard various Kamino vaults

- **Authorization**: [Governance Poll 1606](https://vote.sky.money/polling/QmdomJ7o)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-prime-technical-scope-parameter-change-for-upcoming-spell/27406)

Various Kamino vaults will be onboarded on Solana.

##### [Solana] Onboard various Drift vaults

- **Authorization**: [Governance Poll 1606](https://vote.sky.money/polling/QmdomJ7o)
- **Proposal**: [Forum Post](https://forum.sky.money/t/november-27-2025-prime-technical-scope-parameter-change-for-upcoming-spell/27406)

Various Drift vaults will be onboarded on Solana.

## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
