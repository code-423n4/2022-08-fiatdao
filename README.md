# ✨ So you want to sponsor a contest

This `README.md` contains a set of checklists for our contest collaboration.

Your contest will use two repos: 
- **a _contest_ repo** (this one), which is used for scoping your contest and for providing information to contestants (wardens)
- **a _findings_ repo**, where issues are submitted (shared with you after the contest) 

Ultimately, when we launch the contest, this contest repo will be made public and will contain the smart contracts to be reviewed and all the information needed for contest participants. The findings repo will be made public after the contest report is published and your team has mitigated the identified issues.

Some of the checklists in this doc are for **C4 (🐺)** and some of them are for **you as the contest sponsor (⭐️)**.

---

# Contest prep

## ⭐️ Sponsor: Contest prep
- [ ] Provide a self-contained repository with working commands that will build (at least) all in-scope contracts, and commands that will run tests producing gas reports for the relevant contracts.
- [ ] Make sure your code is thoroughly commented using the [NatSpec format](https://docs.soliditylang.org/en/v0.5.10/natspec-format.html#natspec-format).
- [ ] Modify the bottom of this `README.md` file to describe how your code is supposed to work with links to any relevent documentation and any other criteria/details that the C4 Wardens should keep in mind when reviewing. ([Here's a well-constructed example.](https://github.com/code-423n4/2021-06-gro/blob/main/README.md))
- [ ] Please have final versions of contracts and documentation added/updated in this repo **no less than 24 hours prior to contest start time.**
- [ ] Be prepared for a 🚨code freeze🚨 for the duration of the contest — important because it establishes a level playing field. We want to ensure everyone's looking at the same code, no matter when they look during the contest. (Note: this includes your own repo, since a PR can leak alpha to our wardens!)
- [ ] Promote the contest on Twitter (optional: tag in relevant protocols, etc.)
- [ ] Share it with your own communities (blog, Discord, Telegram, email newsletters, etc.)
- [ ] Optional: pre-record a high-level overview of your protocol (not just specific smart contract functions). This saves wardens a lot of time wading through documentation.
- [ ] Delete this checklist and all text above the line below when you're ready.

---

# FIAT DAO veFDT contest details
- $33,250 USDC main award pot
- $1,750 USDC gas optimization award pot
- Join [C4 Discord](https://discord.gg/code4rena) to register
- Submit findings [using the C4 form](https://code4rena.com/contests/2022-08-fiat-dao-vefdt-contest/submit)
- [Read our guidelines for more details](https://docs.code4rena.com/roles/wardens)
- Starts August 12, 2022 20:00 UTC
- Ends August 15, 2022 20:00 UTC

## Contracts
## Scope
### Files in scope
|File|[SLOC](#nowhere "(nSLOC, SLOC, Lines)")|[Coverage](#nowhere "(Lines hit / Total)")|
|:-|:-:|:-:|
|_Contracts (2)_|
|[contracts/features/Blocklist.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/features/Blocklist.sol) [🖥](#nowhere "Uses Assembly")|[27](#nowhere "(nSLOC:27, SLOC:27, Lines:44)")|[100.00%](#nowhere "(Hit:10 / Total:10)")|
|[contracts/VotingEscrow.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/VotingEscrow.sol) [📤](#nowhere "Initiates ETH Value Transfer")|[670](#nowhere "(nSLOC:603, SLOC:670, Lines:905)")|[97.52%](#nowhere "(Hit:314 / Total:322)")|
|Total (over 2 files):| [697](#nowhere "(nSLOC:630, SLOC:697, Lines:949)")| [97.59%](#nowhere "Hit:324 / Total:332")|


### Direct parent contracts of in-scope contracts (not in scope)
Interfaces and abstracts should be added to scope - wardens will have to review them regardless, and will ask about them (☢️ do not include this line if copying tables to your `README.md` ☢️)
|File|[SLOC](#nowhere "(nSLOC, SLOC, Lines)")|[Coverage](#nowhere "(Lines hit / Total)")|
|:-|:-:|:-:|
|_Interfaces (1)_|
|[contracts/interfaces/IVotingEscrow.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/interfaces/IVotingEscrow.sol)|[20](#nowhere "(nSLOC:14, SLOC:20, Lines:66)")|[100.00%](#nowhere "(Hit:0 / Total:0)")|
|Total (over 1 file):| [20](#nowhere "(nSLOC:14, SLOC:20, Lines:66)")| [100.00%](#nowhere "Hit:0 / Total:0")|


### Other contracts directly imported by in-scope contracts (not in scope)
Interfaces and abstracts should be added to scope - wardens will have to review them regardless, and will ask about them (☢️ do not include this line if copying tables to your `README.md` ☢️)
|File|[SLOC](#nowhere "(nSLOC, SLOC, Lines)")|[Coverage](#nowhere "(Lines hit / Total)")|
|:-|:-:|:-:|
|_Interfaces (2)_|
|[contracts/interfaces/IBlocklist.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/interfaces/IBlocklist.sol)|[4](#nowhere "(nSLOC:4, SLOC:4, Lines:8)")|[100.00%](#nowhere "(Hit:0 / Total:0)")|
|[contracts/interfaces/IERC20.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/interfaces/IERC20.sol)|[25](#nowhere "(nSLOC:16, SLOC:25, Lines:35)")|[100.00%](#nowhere "(Hit:0 / Total:0)")|
|Total (over 2 files):| [29](#nowhere "(nSLOC:20, SLOC:29, Lines:43)")| [100.00%](#nowhere "Hit:0 / Total:0")|


### All other source contracts (not in scope)
|File|[SLOC](#nowhere "(nSLOC, SLOC, Lines)")|[Coverage](#nowhere "(Lines hit / Total)")|
|:-|:-:|:-:|
|_Contracts (2)_|
|[contracts/libraries/ReentrancyBlock.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/libraries/ReentrancyBlock.sol)|[10](#nowhere "(nSLOC:10, SLOC:10, Lines:18)")|[0.00%](#nowhere "(Hit:0 / Total:4)")|
|[contracts/libraries/Authorizable.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/libraries/Authorizable.sol)|[31](#nowhere "(nSLOC:31, SLOC:31, Lines:59)")|[40.00%](#nowhere "(Hit:4 / Total:10)")|
|_Abstracts (2)_|
|[contracts/libraries/ERC20PermitWithMint.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/libraries/ERC20PermitWithMint.sol)|[34](#nowhere "(nSLOC:34, SLOC:34, Lines:70)")|[41.67%](#nowhere "(Hit:5 / Total:12)")|
|[contracts/libraries/ERC20Permit.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/libraries/ERC20Permit.sol) [🧮](#nowhere "Uses Hash-Functions") [🔖](#nowhere "Handles Signatures: ecrecover")|[122](#nowhere "(nSLOC:100, SLOC:122, Lines:244)")|[62.86%](#nowhere "(Hit:22 / Total:35)")|
|_Interfaces (1)_|
|[contracts/interfaces/IERC20Permit.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/interfaces/IERC20Permit.sol)|[15](#nowhere "(nSLOC:7, SLOC:15, Lines:62)")|[100.00%](#nowhere "(Hit:0 / Total:0)")|
|Total (over 5 files):| [212](#nowhere "(nSLOC:182, SLOC:212, Lines:453)")| [50.82%](#nowhere "Hit:31 / Total:61")|


## External imports
* **@openzeppelin/contracts/security/ReentrancyGuard.sol**
  * [contracts/VotingEscrow.sol](https://github.com/code-423n4/2022-08-fiatdao/blob/main/contracts/VotingEscrow.sol)


## All-in-one command
```
export ALCHEMY_MAINNET_API_KEY=<your-api-key-goes-here> && rm -Rf 2022-08-fiatdao || true && git clone https://github.com/code-423n4/2022-08-fiatdao && cd 2022-08-fiatdao && npm install && npm run build && npm run test
```

# veFDT
A solidity implementation of Curve's voting-escrow with additional features outlined below.

**Lock delegation**
Users may delegate ther lock to another user whereby they give the delegatee control over their lock expiration and balance (i.e. voting power). Both users, the delegator and the delegatee, need to have an active lock in place at the time of delegation. Moreover, the delegatee's lock expiration needs to be longer than the delegator's.

**Lock quitting**
A non-expired lock may be quitted by the lock owner anytime. The lock cannot be delegated at the time of quitting and the quitter pays a penalty proportional to the remaining lock duration.

**Optimistic SmartWallet approval**
*SmartWallets* (i.e. contracts) can create a lock without being approved first. However, the veFDT owner maintains a Blocklist where SmartWallets may be blocked from further interacting with the system. The Blocklist only allows the owner to block contracts but not EOAs. Blocked SmartWallets may still undelegate (if delegated prior to the blocking) and quit their lock (by paying the penalty) or withdraw once the lock expired.

## 🏄 Quickstart

```bash
npm install
```
```bash
npm run build
```
```bash
npm run test
```

**Note:** We use hardhat and Alchemy web3 provider in order to test against Ethereum mainnet state. Make sure to configure an Alchemy API endpoint with a valid key before running the `test` script:

```bash
export ALCHEMY_MAINNET_API_KEY=[ALCHEMY_KEY]
```

## Voting-escrow math
The veFDT contract implements the same checkpoint mathematics than the original Curve VotingEscrow.vy contract. The new features leverage this math in order to void or redirect (i.e. delegate) a lock's virtual balance. More details about how the various lock operations interact with Curve's checkpoint math can be found [here](https://github.com/code-423n4/2022-08-fiatdao/blob/main/CheckpointMath.md).

## Source
- Curve Finance: Original concept and implementation in Vyper ([Source](https://github.com/curvefi/curve-dao-contracts/blob/master/contracts/VotingEscrow.vy))
- mStable: Forking Curve's Vyper contract and porting to Solidity including math tests ([Source](https://github.com/mstable/mStable-contracts/blob/master/contracts/governance/IncentivisedVotingLockup.sol)) 

