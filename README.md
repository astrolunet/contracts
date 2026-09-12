# Astrolune Contracts

A collection of reusable Trocto smart contracts for the Astrolune blockchain.

## Structure

```
contracts/
  token/
    fungible.tc          ERC-20 fungible token
    mintable.tc          Owner-controlled mintable token with cap
    governance_token.tc  Voting-weight token with checkpoints
  nft/
    collectible.tc       ERC-721 NFT with operator approvals
    factory.tc           NFT collection deployer
  governance/
    governor.tc          On-chain proposal and voting
    timelock.tc          Delayed execution for governance
  security/
    multisig.tc          Multi-signature wallet
    access_control.tc    Role-based access control
    pausable.tc          Emergency pause mechanism
  defi/
    staking.tc           Token staking with reward accumulation
    vesting.tc           Linear token vesting with revocation
    liquidity_pool.tc    Constant-product AMM (x*y=k)
  bridge/
    bridge.tc            Cross-chain lock-and-mint bridge
  oracle/
    oracle.tc            Decentralized price feed oracle
  factory/
    deployer.tc          Contract deployment factory
```

## Contracts

### Token

| Contract | Description |
|---|---|
| [`fungible.tc`](token/fungible.tc) | ERC-20 fungible token with transfer, approve, burn |
| [`mintable.tc`](token/mintable.tc) | Owner-controlled minting with supply cap and pause |
| [`governance_token.tc`](token/governance_token.tc) | Voting power with block-based checkpoints and delegation |

### NFT

| Contract | Description |
|---|---|
| [`collectible.tc`](nft/collectible.tc) | ERC-721 NFT with operator approvals, mint, burn |
| [`factory.tc`](nft/factory.tc) | Deploy and track NFT collections |

### Governance

| Contract | Description |
|---|---|
| [`governor.tc`](governance/governor.tc) | Proposal creation, token-weighted voting, execution |
| [`timelock.tc`](governance/timelock.tc) | Mandatory delay between queueing and executing |

### Security

| Contract | Description |
|---|---|
| [`multisig.tc`](security/multisig.tc) | Multi-sig wallet with configurable quorum |
| [`access_control.tc`](security/access_control.tc) | Role-based permissions (RBAC) |
| [`pausable.tc`](security/pausable.tc) | Emergency pause/unpause for contracts |

### DeFi

| Contract | Description |
|---|---|
| [`staking.tc`](defi/staking.tc) | Stake tokens, earn block-based rewards |
| [`vesting.tc`](defi/vesting.tc) | Linear vesting with optional revocation |
| [`liquidity_pool.tc`](defi/liquidity_pool.tc) | Two-token AMM with 0.3% fee |

### Bridge

| Contract | Description |
|---|---|
| [`bridge.tc`](bridge/bridge.tc) | Lock-and-mint bridge with relayer quorum |

### Oracle

| Contract | Description |
|---|---|
| [`oracle.tc`](oracle/oracle.tc) | Multi-reporter price feed with heartbeat |

### Factory

| Contract | Description |
|---|---|
| [`deployer.tc`](factory/deployer.tc) | Deploy and track contract instances |

## Usage

Compile any contract with the Trocto compiler:

```bash
trocto contracts/token/fungible.tc -o fungible.bin
```

Inspect the lowered Regol IR:

```bash
trocto contracts/token/fungible.tc --emit-regol
```

Deploy via a DEPLOY transaction with the compiled container binary.

## Adding a Contract

1. Place the `.tc` file in the appropriate category directory
2. Include the copyright header and compile instructions in the file comment
3. Add an entry to the relevant table above
4. Submit a pull request

## License

MIT
