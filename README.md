# ✨ So you want to sponsor a contest

This `README.md` contains a set of checklists for our contest collaboration.

Your contest will use two repos: 
- **a _contest_ repo** (this one), which is used for scoping your contest and for providing information to contestants (wardens)
- **a _findings_ repo**, where issues are submitted (shared with you after the contest) 

Ultimately, when we launch the contest, this contest repo will be made public and will contain the smart contracts to be reviewed and all the information needed for contest participants. The findings repo will be made public after the contest report is published and your team has mitigated the identified issues.

Some of the checklists in this doc are for **C4 (🐺)** and some of them are for **you as the contest sponsor (⭐️)**.

---

# Contest setup

## ⭐️ Sponsor: Provide contest details

Under "SPONSORS ADD INFO HERE" heading below, include the following:

- [ ] Create a PR to this repo with the below changes:
- [ ] Name of each contract and:
  - [ ] source lines of code (excluding blank lines and comments) in each
  - [ ] external contracts called in each
  - [ ] libraries used in each
- [ ] Describe any novel or unique curve logic or mathematical models implemented in the contracts
- [ ] Does the token conform to the ERC-20 standard? In what specific ways does it differ?
- [ ] Describe anything else that adds any special logic that makes your approach unique
- [ ] Identify any areas of specific concern in reviewing the code
- [ ] Add all of the code to this repo that you want reviewed


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

[ ⭐️ SPONSORS ADD INFO HERE ]
## Contracts
[VotingEscrow.sol](./contracts/VotingEscrow.sol) -
839 sloc -
External contracts called: ERC20 token contract (LP FDT-ETH)

[Blocklist.sol](./contracts/features/Blocklist.sol) - 
38 sloc - 
External contracts called : VotingEscrow.sol

# veFDT
A solidity implementation of Curve's voting-escrow with additional features outlined below.

**Lock delegation**
Users may delegate ther lock to another user whereby they give the delegatee control over their lock expiration and balance (i.e. voting power). Both users, the delegator and the delegatee, need to have an active lock in place at the time of delegation. Moreover, the delegatee's lock expiration needs to be longer than the delegator's.

**Lock quitting**
A non-expired lock may be quitted by the lock owner anytime. The lock cannot be delegated at the time of quitting and the quitter pays a penalty proportional to the remaining lock duration.

**Optimistic SmartWallet approval**
*SmartWallets* (i.e. contracts) can create a lock without being approved first. However, the veFDT owner maintains a Blocklist where SmartWallets may be blocked from further interacting with the system. The Blocklist only allows the owner to block contracts but not EOAs. Blocked SmartWallets may still undelegate (if delegated prior to the blocking) and quit their lock (by paying the penalty) or withdraw once the lock expired.

## Quickstart
Guidelines can be found [here](./Guidelines.md).
