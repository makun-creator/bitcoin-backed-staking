# BitStake Protocol

## Decentralized Bitcoin-Backed Staking on Stacks

BitStake is a Bitcoin-native staking protocol built on the Stacks Layer 2 blockchain. It enables users to stake STX tokens, earn rewards with tiered multipliers, and participate in decentralized governance — all while enhancing the Bitcoin ecosystem with secure and composable DeFi primitives.

## Overview

**BitStake** allows users to:

* **Stake STX tokens** with optional lock periods to earn dynamic rewards.
* **Unlock tier-based benefits**, including higher multipliers and advanced features.
* **Participate in governance** by creating and voting on proposals.
* **Securely unstake** using a cooldown mechanism to prevent abuse and enhance protocol safety.

## Features

### Staking

* Flexible STX staking with optional lock periods (no lock, 1 month, 2 months).
* Locking STX increases reward multipliers.

### Tier System

* Users are assigned tier levels based on their stake amount.
* Each tier grants specific features and reward multipliers:

  * **Tier 1:** ≥ 1M STX (1x rewards)
  * **Tier 2:** ≥ 5M STX (1.5x rewards)
  * **Tier 3:** ≥ 10M STX (2x rewards)

### Governance

* Token holders with sufficient voting power can create and vote on proposals.
* Governance includes a minimum voting threshold to execute proposals.

### Security & Controls

* Cooldown periods are enforced before unstaking can be completed.
* Emergency and pause modes are built in for protocol safety.

## Contract Structure

### Fungible Token

* `ANALYTICS-TOKEN` (placeholder for potential incentive/distribution mechanics)

### Key Maps and Variables

* `UserPositions`: Tracks staking, voting power, and tier level.
* `StakingPositions`: Tracks lock period, cooldown, and rewards.
* `TierLevels`: Defines each tier’s minimum stake and benefits.
* `Proposals`: Governance structure for community decisions.

## Public Functions

| Function              | Description                                  |
| --------------------- | -------------------------------------------- |
| `initialize-contract` | Initializes tier definitions (owner only).   |
| `stake-stx`           | Stake STX with an optional lock period.      |
| `initiate-unstake`    | Start the cooldown period to unstake.        |
| `complete-unstake`    | Withdraw STX after cooldown expires.         |
| `create-proposal`     | Propose a new governance change.             |
| `vote-on-proposal`    | Vote for or against a proposal.              |
| `pause-contract`      | Pause all sensitive operations (owner only). |
| `resume-contract`     | Resume operations (owner only).              |

## Read-Only Functions

| Function             | Description                              |
| -------------------- | ---------------------------------------- |
| `get-contract-owner` | Returns the protocol owner.              |
| `get-stx-pool`       | Returns the current STX pool.            |
| `get-proposal-count` | Returns the number of proposals created. |

## Internal Logic

* **Rewards**: Based on base rate, user’s reward multiplier, and staking duration.
* **Tier Assignment**: Determined dynamically upon staking based on total amount.
* **Validation**: Strict input checks on lock periods, voting descriptions, and durations.

## Security Measures

* Only the contract owner can pause/resume the protocol.
* Cooldowns protect against instant withdrawals.
* Minimum stake thresholds prevent spam and ensure economic security.

## Built With

* [Clarity Language](https://docs.stacks.co/docs/clarity)
* [Stacks Blockchain](https://stacks.co/)
* Bitcoin-secured smart contracts, powered by Proof-of-Transfer (PoX).

## Contributing

Contributions and community feedback are welcome! Please open issues or submit PRs to improve BitStake.
