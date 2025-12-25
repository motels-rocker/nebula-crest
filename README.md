# Nebula Crest (Built for Base)

Nebula Crest is a read-only onchain toolkit designed for Base Mainnet and Base Sepolia. It allows you to interact with Base networks, inspect blockchain states, check balances, validate network identity, and interact with deployed contracts, all with verification through Basescan.

## Key Features

- **Coinbase Wallet SDK** for EIP-1193 wallet integration  
- **Base Mainnet (8453)** and **Base Sepolia (84532)** chainId verification  
- **Network snapshot functionality** for retrieving block height, gas usage, and gas price  
- **Address inspection** to check balance, transaction count, and bytecode presence  
- **ERC-20 token inspection** to get token details such as metadata, total supply, and balance  
- **Direct Basescan links** for verifying contract and address details independently  

---

## Project Layout

- **app/nebula-crest.ts**  
  The main browser-based script responsible for connecting to Coinbase Wallet and executing Base RPC queries.

- **config/base.networks.json**  
  Contains the configuration for Base networks, including RPC URLs, explorers, and chainIds for both Base Mainnet and Base Sepolia.

- **docs/architecture.md**  
  A technical breakdown of the project architecture, design decisions, and its alignment with Base's ecosystem.

- **docs/testnet-validation.md**  
  Documentation detailing the validation process for contracts deployed on Base Sepolia during testnet phases.

- **contracts/**  
  Solidity contracts deployed on Base Sepolia for testnet validation:
  - `mapping.sol` — A Solidity contract that demonstrates mappings (key-value storage)
  - `errors.sol` — Helps save gas by reducing the size of error messages compared to revert strings

- **package.json**  
  Manifest containing dependencies, including references to relevant Base and Coinbase repositories.

- **README.md**  
  The main documentation for setting up, running, and understanding the project.

---

## Supported Networks

- **Base Sepolia**  
  ChainId (decimal): 84532  
  Explorer: [sepolia.basescan.org](https://sepolia.basescan.org)

- **Base Mainnet**  
  ChainId (decimal): 8453  
  Explorer: [basescan.org](https://basescan.org)

---

## How It Works

This repository allows developers to access and interact with Base networks by:
- Connecting Coinbase Wallet via the **Coinbase Wallet SDK**
- Interacting with the **Base RPC** to fetch data about blocks, transactions, and balances
- Allowing for quick verification via **Basescan**

It offers a quick and transparent way to ensure that your contracts and interactions with Base are valid and working as expected before moving to production.

---

## Dependencies

The project leverages several key dependencies from the Coinbase and Base ecosystems:
- **Coinbase Wallet SDK** for seamless wallet connection
- **OnchainKit** for Base-native functionality and interaction
- **Viem** for efficient, typed communication with Base’s RPC
- Direct dependencies from **Base** and **Coinbase GitHub repositories**

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Author Information

GitHub: [https://github.com/motels-rocker](https://github.com/motels-rocker)  

Email: motels.rocker-0h@icloud.com

Twitter: [https://x.com/saberhammer51](https://x.com/saberhammer51)  

## Testnet Deployment (Base Sepolia)

In preparation for production deployment, the following contracts have been deployed to the Base Sepolia test network to validate functionality:

**Network**: Base Sepolia  
**ChainId (decimal)**: 84532  
**Explorer**: [sepolia.basescan.org](https://sepolia.basescan.org)

**Contract mapping.sol address**:  
0x2F0c1B318D8EE565f5aC1C45CF6C00647C68bb63 

**Deployment and verification**:
- [Deployment link](https://sepolia.basescan.org/address/0x2F0c1B318D8EE565f5aC1C45CF6C00647C68bb63 )
- [Code verification](https://sepolia.basescan.org/0x2F0c1B318D8EE565f5aC1C45CF6C00647C68bb63/0#code)

**Contract errors.sol address**:  
0x390b6742107ed3F9B5c865e6b9AB116d626Ce707

**Deployment and verification**:
- [Deployment link](https://sepolia.basescan.org/address/0x390b6742107ed3F9B5c865e6b9AB116d626Ce707)
- [Code verification](https://sepolia.basescan.org/0x390b6742107ed3F9B5c865e6b9AB116d626Ce707/0#code)

These deployments are part of the process to validate tooling and network interactions before deploying on Base Mainnet.
