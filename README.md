## Short intro
The project is aimed at providing a secure and private voting system that uses blockchain technology and zero-knowledge proofs (ZK proofs) to ensure the anonymity of voters. The decentralized voting tool will allow voters to cast their votes anonymously without the need for a central authority or intermediary. The use of ZK proofs will provide additional privacy protections by ensuring that voter identities are not revealed, while the use of blockchain technology will ensure that the voting results are transparent and tamper-proof. ~~ ChatGPT



## What's decentralized private voting?
In a decentralized voting system, each participant has an equal say in the outcome of the vote,
and there is no central authority that can manipulate or control the results.
Voting plays quite an important role in the working of an administrative structure and talking
in an ideal sense, all the voting processes should be `secure` and `transparent`

These are the various steps involved in the conduction of a voting process :
A :white_check_mark: or :negative_squared_cross_mark: denotes whether our current implementation makes
this step better over traditional approaches.

-> Creation of a Proposal  :white_check_mark:
== Anyone with an Ethereum Wallet can create a new proposal without revealing his true identity.
   No checks whatsoever is involved while creation of a proposal.

   The Proposal Maker fills the necessary fields required in the `Proposal Schema` which then gets casted
   to IPFS(InterPlanetary File System).
   IPFS then returns a CID hash which gets logged in to the `Voting Factory Contract`.
   Storing the CID hash in the smart contract `allows anyone to fetch the Proposal Content` from IPFS
   so that they don't have to trust on our UI and can verify the content themselves.

   The `Voting Factory Contract` manages the operations of all the Proposals.
   This smart contract deploys a new instance of `Proposal.sol` every time a new proposal is created
   and maintains a registry of all the ongoing proposals.
   All the core voting operations logic such as casting vote, submitted zkProof, is handled by the `Proposal.sol` contract.

-> Registration and Distribution of Voting rights

-> Casting of Votes

-> Vote tallying




### Tasks Left TO Figure Out
- [ ] We will use ZKProofs to hide the voter's identity. If the user's identity is going to be private
      then should we opt for an alternate method of distributing voting rights than the current method that
      everyone must have an Ethereum Wallet? The focus of this is to provide better UX for voters.
- [ ] Define `ProposalSchema`



## User-flow
-> Entities involved : `Proposal Maker`, `Proposal`,  `Voters`

->






# Turborepo starter

This is an official npm starter turborepo.


This turborepo uses [npm](https://www.npmjs.com/) as a package manager. It includes the following packages/apps:

- `docs`: a [Next.js](https://nextjs.org/) app
- `web`: another [Next.js](https://nextjs.org/) app
- `protocol` : containing all the smart contracts
- `circuits` : contains the zk circuits written in circom
- `ui`: a stub React component library shared by both `web` and `docs` applications
- `eslint-config-custom`: `eslint` configurations (includes `eslint-config-next` and `eslint-config-prettier`)
- `tsconfig`: `tsconfig.json`s used throughout the monorepo

To build all apps and packages, run the following command:

```
cd my-turborepo
npm run build
```

To develop all apps and packages, run the following command:

```
cd my-turborepo
npm run dev
```
