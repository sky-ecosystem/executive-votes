---
title: Template - [Executive Vote] Allocator 4 Technical Launch, Monthly Settlement Cycle for September 2025, Ranked Delegate Compensation, Atlas Core Development Compensation, Execute Prime Agent Proxy Spells - October 16, 2025
summary: $summary
date: 2025-10-16T00:00:00.000Z
address: "$spell_address"
---

# [Executive Proposal] Allocator 4 Technical Launch, Monthly Settlement Cycle for September 2025, Ranked Delegate Compensation, Atlas Core Development Compensation, Star Proxy Spells - October 16, 2025

The Governance Facilitators, Sidestream, and Dewiz have placed an executive proposal into the voting system. SKY holders should vote for this proposal if they support the following alterations to the Sky Protocol.

If you are new to voting in the Sky Protocol, please see the [voting guide](https://manual.makerdao.com/governance/voting-in-makerdao/on-chain-governance) to learn how voting works.

---

## Executive Summary

If this executive proposal passes, the following **actions** will occur within the Sky Protocol:

- The Allocator Vault and associated contracts for Launch Agent 4 will be initialized.
- The Monthly Settlement Cycle for September 2025 will be executed.
- A total of **23,824 USDS** will be distributed to 6 Ranked Delegates as compensation for September 2025.
- A total of **78,188 USDS** and **618,000 SKY** will be distributed as Atlas Core Development compensation for October 2025.
- Prime Agent proxy spells for Spark and Grove will be executed.

**Voting for this executive proposal will place your SKY in support of the actions outlined above.**

Unless otherwise noted, the actions listed above are subject to the [GSM Pause Delay](https://sky-atlas.powerhouse.io/A.1.9.2.1_Pause_Delay/a98b8227-95f6-4711-9d8d-f52cbc6ad2d0|0db30758e055). This means that if this executive proposal passes, the changes and additions listed above will only become active in the Sky Protocol after the GSM Pause Delay has expired. The GSM Pause Delay is currently set to [**24 hours**](https://sky-atlas.powerhouse.io/A.1.9.2.1.2_Pause_Delay_Current_Value/09d2514b-3169-4755-a654-2c774456980d|0db30758e055d2d0).

This executive proposal includes an office-hours modifier that means that it **can only be executed between 14:00 and 21:00 UTC, Monday - Friday**.

If this executive proposal does not pass within 30 days, then it will expire and can no longer have any effect on the Sky Protocol.

---

## Proposal Details

### Allocator 4 Technical Launch

- **Authorization**: [Facilitator approval]($TBD), [Atlas Authorization]($TBD)
- **Proposal**: [Forum Post](https://forum.sky.money/t/technical-scope-launch-of-the-agent-4-allocation-system/27314)

If this executive proposal passes, then the technical launch of Allocator 4 will be carried out by calling [AllocatorInit.initIlk](https://github.com/makerdao/dss-allocator/blob/226584d3b179d98025497815adb4ea585ea0102d/deploy/AllocatorInit.sol#L97-L164) with the following parameters:

- sharedInstance.oracle: PIP_ALLOCATOR from [chainlog](https://chainlog.sky.money/);
- sharedInstance.roles: ALLOCATOR_ROLES from chainlog;
- sharedInstance.registry: ALLOCATOR_REGISTRY from chainlog;
- ilkInstance.owner: MCD_PAUSE_PROXY from chainlog;
- ilkInstance.vault: [0xF275110dFE7B80df66a762f968f59B70BABE2b29](https://etherscan.io/address/0xF275110dFE7B80df66a762f968f59B70BABE2b29) (AllocatorVault contract);
- ilkInstance.buffer: [0x51E9681D7a05abFD33EfaFd43e5dd3Afc0093F1D](https://etherscan.io/address/0x51E9681D7a05abFD33EfaFd43e5dd3Afc0093F1D) (AllocatorBuffer contract);
- cfg.ilk: ALLOCATOR-OBEX-A;
- cfg.duty: 1 * 10**27 (0%);
- cfg.gap: 10 million USDS;
- cfg.maxLine: 10 million USDS;
- cfg.ttl: 86,400 seconds (24 hours);
- cfg.allocatorProxy: [0x8be042581f581E3620e29F213EA8b94afA1C8071](https://etherscan.io/address/0x8be042581f581E3620e29F213EA8b94afA1C8071) (SubProxy contract);
- cfg.ilkRegistry: ILK_REGISTRY from chainlog;

The initialization script will create a PIP_ALLOCATOR_OBEX_A entry in the chainlog, this is not necessary and will be removed.

ALLOCATOR-OBEX-A will be added to the [Debt Ceiling Breaker (LINE_MOM)](https://sky-atlas.powerhouse.io/A.1.9.3.2.3_Debt_Ceiling_Breaker_Exception/8c27b081-2db5-4e8f-9b5c-f5cf0f8d3102|0db30758e055352c).

### September 2025 Monthly Settlement Cycle

- **Authorization**: [Core GovOps Approval](https://forum.sky.money/t/msc-2-settlement-summary-september-2025-spark-only-initial-calculations/27286/4), [Core Facilitator Approval](https://forum.sky.money/t/msc-2-settlement-summary-september-2025-spark-only-initial-calculations/27286/5), [Atlas Authorization](https://sky-atlas.powerhouse.io/A.2.5_Sky_Core_Monthly_Settlement_Cycle/1d8f2ff0-8d73-807c-80f0-e58dde70cc27|9e1f)
- **Proposal**: [Forum post](https://forum.sky.money/t/msc-2-settlement-summary-september-2025-spark-only-initial-calculations/27286)

If this executive proposal passes, then the following steps to execute the September 2025 Monthly Settlement Cycle will be taken:

#### Spark

- Mint **16,931,086 USDS** debt in ALLOCATOR-SPARK-A and transfer the amount to the Surplus Buffer.
- Send **3,827,201 USDS** from the Surplus Buffer to the Spark SubProxy at [0x3300f198988e4C9C63F75dF86De36421f06af8c4](https://etherscan.io/address/0x3300f198988e4C9C63F75dF86De36421f06af8c4).

#### Grove

- Mint **6,382,973 USDS** debt in ALLOCATOR-BLOOM-A and transfer the amount to the Surplus Buffer.
- Send **104,924 USDS** from the Surplus Buffer to the Grove SubProxy at [0x1369f7b2b38c76B6478c0f0E66D94923421891Ba](https://etherscan.io/address/0x1369f7b2b38c76B6478c0f0E66D94923421891Ba).

### Ranked Delegate Compensation for September 2025

- **Authorization**: [Atlas Authorization](https://sky-atlas.powerhouse.io/A.1.5.7.1_AD_Monthly_Compensation_Cycle/117f2ff0-8d73-806f-87d7-e6713a7fe64f|0db3af4e4161)
- **Proposal**: [Forum post](https://forum.sky.money/t/september-2025-ranked-delegate-compensation/27305)

If this executive proposal passes, then a total of **23,824 USDS** will be distributed to 6 Ranked Delegates as follows:

| Delegate    | Amount (USDS) | Address                                                                                                               |
|-------------|---------------|-----------------------------------------------------------------------------------------------------------------------|
| AegisD      | 4,000         | [0x78C180CF113Fe4845C325f44648b6567BC79d6E0](https://etherscan.io/address/0x78C180CF113Fe4845C325f44648b6567BC79d6E0) |
| BLUE        | 4,000         | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |
| Bonapublica | 4,000         | [0x167c1a762B08D7e78dbF8f24e5C3f1Ab415021D3](https://etherscan.io/address/0x167c1a762B08D7e78dbF8f24e5C3f1Ab415021D3) |
| Cloaky      | 4,000         | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |
| Tango       | 4,000         | [0xB2B86A130B1EC101e4Aed9a88502E08995760307](https://etherscan.io/address/0xB2B86A130B1EC101e4Aed9a88502E08995760307) |
| Sky Staking | 3,824         | [0x05c73AE49fF0ec654496bF4008d73274a919cB5C](https://etherscan.io/address/0x05c73AE49fF0ec654496bF4008d73274a919cB5C) |

### Atlas Core Development Payments for October 2025

- **Authorization**: [Atlas Authorization](https://sky-atlas.powerhouse.io/Budget_And_Participation_Requirements/4c698938-1a11-4486-a568-e54fc6b0ce0c%7C0db3af4e)
- **Proposal**: [Forum post](https://forum.sky.money/t/atlas-core-development-payment-requests-october-2025/27293)

If this executive proposal passes, then a total of **78,188 USDS** and **618,000 SKY** will be distributed as Atlas Core Development payments fro October 2025 as follows:

#### USDS

#### USDS Payments

| Recipient | Amount (USDS) | Address                                                                                                               |
|-----------|--------------:|-----------------------------------------------------------------------------------------------------------------------|
| Kohla     | 11,604        | [0x73dFC091Ad77c03F2809204fCF03C0b9dccf8c7a](https://etherscan.io/address/0x73dFC091Ad77c03F2809204fCF03C0b9dccf8c7a) |
| Cloaky    | 16,417        | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |
| BLUE      | 50,167        | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |

#### SKY Payments

| Recipient | Amount (SKY) | Address                                                                                                               |
|-----------|-------------:|-----------------------------------------------------------------------------------------------------------------------|
| Cloaky    | 288,000      | [0x9244F47D70587Fa2329B89B6f503022b63Ad54A5](https://etherscan.io/address/0x9244F47D70587Fa2329B89B6f503022b63Ad54A5) |
| BLUE      | 330,000      | [0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf](https://etherscan.io/address/0xb6C09680D822F162449cdFB8248a7D3FC26Ec9Bf) |

### Prime Agent Proxy Spells



## Review

Community debate on these topics can be found on the Sky [Governance forum](https://forum.sky.money/). Please review any linked threads to inform your position before voting.

---

## Resources

Additional information about the Governance process can be found in the [Operational Manual](https://manual.makerdao.com).

To add current and upcoming votes to your calendar, please see the [Sky Governance Calendar](https://manual.makerdao.com/makerdao/calendars/governance-calendar).
