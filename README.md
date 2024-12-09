# Blockchain Implementation in JavaScript

This project demonstrates a basic implementation of a blockchain using JavaScript. It includes key features such as block mining, chain validation, and the creation of new blocks with proof-of-work (difficulty-based mining).

## Files

- **block.js**: Contains the implementation of the `Block` class and `Blockchain` class.

## Description

### Block Class
The `Block` class represents an individual block in the blockchain. It contains the following properties:
- `index`: The position of the block in the chain.
- `timestamp`: The time at which the block was created.
- `data`: The information stored in the block.
- `previousHash`: The hash of the previous block in the chain.
- `hash`: The unique hash of the current block.
- `nonce`: A counter used for mining the block.

The block has the following methods:
- `calculateHash()`: Calculates the hash of the block using SHA256, including the `index`, `previousHash`, `timestamp`, `data`, and `nonce`.
- `mineBlock(difficulty)`: Mines the block by repeatedly changing the `nonce` until the hash starts with a specific number of leading zeros defined by the `difficulty` level.

### Blockchain Class
The `Blockchain` class represents the entire blockchain. It has the following properties:
- `chain`: An array that holds all the blocks in the blockchain.
- `difficulty`: The level of difficulty for mining a block (number of leading zeros in the hash).

The blockchain has the following methods:
- `createGenesisBlock()`: Creates the first block of the blockchain, also called the genesis block.
- `getLatestBlock()`: Returns the latest block in the chain.
- `addBlock(newBlock)`: Adds a new block to the blockchain after mining it.
- `isChainValid()`: Checks the validity of the blockchain by ensuring that each block's hash matches its calculated hash and that each block points to the previous block correctly.

### Test Blockchain
The script tests the blockchain implementation by creating a new blockchain instance, mining a few blocks, and validating the blockchain's integrity.

## Usage

1. Clone this repository or copy the code into your preferred development environment.
2. Install the required dependency:
   ```bash
   npm install crypto-js
