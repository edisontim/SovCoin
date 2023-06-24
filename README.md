# SovereignCoin

SovereignCoin is a proof-of-concept sovereign zk-rollup built on top of Bitcoin.

## Sovereign rollups

A sovereign rollup is a blockchain that publishes its transactions to another blockchain, typically for ordering, data availability and consensus, but it handles its own settlement. This is the major point that differentiates it from a regular rollup, the DA layer doesn't verify that sovereign rollup TXs are correct. Nodes verifying the sovereign rollup are responsible for verifying that new transactions are correct ([https://celestia.org/learn/sovereign-rollups/an-introduction/#what-is-a-sovereign-rollup](https://celestia.org/learn/sovereign-rollups/an-introduction/#what-is-a-sovereign-rollup))  
If the nodes verify a transaction that was published to the DA layer and it's invalid, they will reject and ignore it. Now, the sovereign rollup is responsible for determining its correct chain, not the DA layer.

## Design decisions

_As this project is part of the grant program of Starkware, the rollup will be very similar to Starknet._

- There will be one centralized sequencer: Madara
- Centralized prover: Sharp
- Usage of ordinals to store the state / validity proofs on Data Availability Layer, Bitcoin
- 
- Light nodes will be able to be verifiers by checking the Data Availability layer.
