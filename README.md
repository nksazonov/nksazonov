# Nikita Sazonov

**Senior Smart Contract Engineer — escrow, custody and state channels.** I design and secure smart contracts that hold user funds, from the state machine and its invariants through audit to mainnet operations.

Prague, Czech Republic (CET) · [sazonov.nks@gmail.com](mailto:sazonov.nks@gmail.com) · [LinkedIn](https://www.linkedin.com/in/nksazonov/)

---

## Selected work

### 1. Nitrolite v1: cross-chain state-channel protocol · 2025–2026

- **What it is:** escrow contracts where two parties co-sign states off-chain and settle on-chain. Funds move only on a state both signed; if the operator stops responding, the user exits through an on-chain challenge. Supports cross-chain deposits, withdrawals and channel migration.
- **What I did:** designed the state machine from scratch (reusing ForceMove's dispute concept), wrote its semi-formal model and security invariants, and owned the Solidity. As de-facto tech lead of a 3–4 person team, took a 3-month, ~100-finding full-stack audit to its deadlines.
- **Result:** six-contract suite deployed to deterministic addresses on **8 mainnets**.
- **Links:** [repo](https://github.com/layer-3/nitrolite) · [contracts](https://github.com/layer-3/nitrolite/tree/main/contracts) · [architecture diagram](https://github.com/layer-3/nitrolite/blob/main/docs/protocol/state_ledger_advancement.png) · [deployments](https://github.com/layer-3/nitrolite/tree/main/contracts/deployments) · [ChannelHub on Etherscan](https://etherscan.io/address/0x1a2f750170474d4c54f8d318d9d4343588b4c4d1)


### 2. LiteVault: multi-chain user-fund vault · 2024–2025

- **What it is:** a per-user, per-token vault with replaceable withdrawal policies and a guaranteed withdrawal window after any policy change, so users can always leave under the old rules.
- **What I did:** owned the on-chain design; led its Hacken audit remediation, deployments and migrations.
- **Result:** [**$1.76M peak TVL**](https://defillama.com/protocol/yellow) (Jan 2025, DefiLlama); Hacken audit with 13 findings, **no Critical/High**.
- **Links:** [contract](https://github.com/layer-3/broker-contracts/blob/master/src/vault/LiteVault.sol) · [Hacken report](https://hacken.io/audits/openware-yellow-network/sca-yellow-network-vault-sept-2024/) · [LiteVault on Etherscan](https://etherscan.io/address/0xb5F3a9dD92270f55e55B7Ac7247639953538A261) · [all deployments](https://github.com/layer-3/clearsync/blob/master/docs/deployments.md)

### 3. Multi-chain threshold custody · 2026

- **What it is:** independent providers observe deposits and withdrawals on EVM, Bitcoin, Solana and XRPL and authorize withdrawals by quorum; balances settle off-chain from quorum-signed receipts.
- **What I did:** owned all Solidity: the EVM `Custody` vault executing EIP-712 withdrawals signed by a provider quorum, with per-depositor nonces and nonce-protected signer rotation, and the on-chain node registry. Wrote the system's security invariants and assumptions; designed walletless Bitcoin deposits through a shared address with attribution markers.
- **Links:** the vault repository is private; the [registry contracts](https://github.com/layer-3/clearnet-sdk/tree/main/contracts/src) are public in [clearnet-sdk](https://github.com/layer-3/clearnet-sdk).

### 4. Ducklings: on-chain NFT breeding game · 2023

- **What I did:** proposed and co-designed the gas-optimized on-chain genome (packed into a single `uint256`), inheritance and randomness model, and implemented the prototype.
- **Result:** the Polygon collection reached [**874,000 NFTs held across 224,000 wallets**](https://web3.okx.com/nft/collection/polygon/yellow-ducklings-1).
- **Links:** [contracts](https://github.com/layer-3/duckies-v1)

### 5. Security audit record · 2022–2026

As the code owner, I remediated 7 external audits and led the remediation of 6 of them:

| Auditor | When | Scope | My role | Public evidence |
| --- | --- | --- | --- | --- |
| Guardian | Mar–Jun 2026 | Nitrolite contracts + off-chain node, ~100 findings | Led as de-facto tech lead: triage, task split, auditor disputes, fixes | Engagement closed with ~99% of fixes applied, before the final report · remediation PRs: [first](https://github.com/layer-3/nitrolite/pull/631), [last](https://github.com/layer-3/nitrolite/pull/846) |
| Guardian | Mar 2026 | Nitewatch `ThresholdCustody` | Designed the audited contract; led remediation | [Review](https://guardian.security/portfolio/yellow/nitewatch-2026-03-08/) |
| Guardian | Mar 2026 | YELLOW Governor, Locker, Token, Treasury | Remediation | [Review](https://guardian.security/portfolio/yellow/yellow-contract-2026-03-08/) |
| Omniscia | Apr–May 2025 | Nitrolite Custody and adjudicators | Finding tracker, triage; led remediation | [Tracker](https://github.com/layer-3/nitrolite/issues/65) |
| Hacken | Sep 2024 | LiteVault, BrokerToken | Led remediation | [Report](https://hacken.io/audits/openware-yellow-network/sca-yellow-network-vault-sept-2024/) |
| Hacken | Feb–Mar 2023 | ClearSync token | Led remediation (privilege separation) | [Report](https://github.com/layer-3/clearsync/blob/master/docs/audits/YellowNetwork_SC%20Audit%20Report_14022023_%5BSA-1068%5D.pdf) |
| Hacken | Feb–Mar 2022 | NeoDAX vesting | Led remediation | Report not public |

### 6. Open source

- **State Channels, with the Consensys State Channels team (2022–2023):** [go-nitro](https://github.com/statechannels/go-nitro/pulls?q=is%3Apr+author%3Anksazonov) (upstream ForceMove helpers, state and outcome hashing, proof handling, consensus tests, gas benchmarks) and [exit-format](https://github.com/statechannels/exit-format/pull/68) (exit equality support).
- **[forge-create](https://github.com/nksazonov/forge-create):** Foundry deployment tool recording address, tx hash, constructor args, commit and chain ID.
- **[chain-rpc](https://github.com/nksazonov/chain-rpc):** Go CLI that discovers public RPC endpoints and validates their chain IDs.
- **Upstream bug reports:** [go-ethereum #31203](https://github.com/ethereum/go-ethereum/issues/31203), [#31323](https://github.com/ethereum/go-ethereum/issues/31323) · [ZeroDev Kernel #88](https://github.com/zerodevapp/kernel/issues/88) · [Pimlico Alto #160](https://github.com/pimlicolabs/alto/issues/160)

### 7. Research and writing

- **[Private Key Security Portal](https://github.com/nksazonov/private-key-security-portal)** (MSc thesis): key generation, custody models, multisig and weighted signatures, social recovery.
- **[Solidity / Yul / Vyper gas comparison](https://github.com/nksazonov/gas-efficacy-pl-analysis):** EVM bytecode and gas efficiency across smart-contract languages.
