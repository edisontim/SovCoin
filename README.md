# SovereignCoin

SovereignCoin is a proof-of-concept sovereign zk-rollup built on top of Bitcoin.

## Sovereign rollups

A sovereign rollup is a blockchain that publishes its transactions to another blockchain, typically for ordering, data availability and consensus, but it handles its own settlement. This is the major point that differentiates it from a regular rollup, the DA layer doesn't verify that sovereign rollup TXs are correct. Nodes verifying the sovereign rollup are responsible for verifying that new transactions are correct ([https://celestia.org/learn/sovereign-rollups/an-introduction/#what-is-a-sovereign-rollup](https://celestia.org/learn/sovereign-rollups/an-introduction/#what-is-a-sovereign-rollup))  
If the nodes verify a transaction that was published to the DA layer and it's invalid, they will reject and ignore it. Now, the sovereign rollup is responsible for determining its correct chain, not the DA layer.

## Design decisions

_As this project is part of the grant program of Starkware, the rollup will be very similar to Starknet._

- Centralized prover: Sharp
- There will be one centralized sequencer: Madara
- Usage of ordinals to store the state transitions / validity proofs on the Data Availability Layer, Bitcoin
- A trusted bridge to transfer funds L1 <> L2
- Light nodes will be able to be verifiers by checking the Data Availability layer.
- Smart contract account logic

## Objectives

Having a functioning Sovereign Rollup on top of Bitcoin, able to process transactions and supporting smart contracts written in Turing complete language, Cairo.