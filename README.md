# Astrolune Contracts

A collection of reusable Trocto smart contracts for the Astrolune blockchain.

## Contracts

| Contract | Description |
|---|---|
| [`token.tc`](token.tc) | ERC-20-style fungible token with transfer, approve, and burn |
| [`nft.tc`](nft.tc) | ERC-721-style non-fungible token with mint, transfer, and burn |
| [`multisig.tc`](multisig.tc) | Multi-signature wallet with configurable quorum |
| [`staking.tc`](staking.tc) | Token staking with reward accumulation |
| [`vesting.tc`](vesting.tc) | Linear token vesting over block duration |

## Usage

Compile any contract with the Trocto compiler:

```bash
trocto contracts/token.tc -o token.bin
```

Inspect the lowered Regol IR:

```bash
trocto contracts/token.tc --emit-regol
```

Deploy via a DEPLOY transaction with the compiled container binary.

## Adding a Contract

1. Create a new `.tc` file following the existing patterns
2. Include compile instructions in the file header comment
3. Add an entry to the table above
4. Submit a pull request

## License

MIT
