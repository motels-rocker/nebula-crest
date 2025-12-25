# Nebula Crest — Architecture Overview

## Overview

Nebula Crest is designed to interact with **Base** networks, focusing on **Base Mainnet** for production and **Base Sepolia** for testnet operations. This document provides a breakdown of the project's architecture, design decisions, and how it aligns with Base’s ecosystem principles.

## Key Design Decisions

### 1. **Base Network Integration**
Nebula Crest is a **Base-first** project, aligning with **Base Mainnet** and **Base Sepolia**.
- **Base Mainnet** (`8453`): The primary network for production.
- **Base Sepolia** (`84532`): Used as the testnet for staging and validation.

All configurations, including RPC URLs and explorers, are stored in `config/base.networks.json` to avoid hardcoded network values and to ensure easy configurability across different environments.

### 2. **Read-only Approach**
The project uses a **read-only first** approach to minimize risk and streamline testing:
- Interacts with the blockchain mainly for **balance checks**, **metadata reads**, and **contract inspections**.
- **No transaction writes** or gas-intensive operations are part of the core logic.
- This simplifies validation and testing, especially on testnets like Base Sepolia.

### 3. **Minimal Dependencies**
We have kept the dependencies minimal and carefully chosen to maintain compatibility with the **Base ecosystem**:
- We prioritize **Base-native** or **Base-compatible** packages wherever possible.
- Avoiding unnecessary packages reduces the attack surface and makes the project easier to audit and maintain.

---

## Base Ecosystem Alignment

### RPC Endpoints
- We use **public RPC endpoints** for Base Mainnet and Base Sepolia, ensuring the project remains decentralized and resilient.
- The RPC configurations are stored in `config/base.networks.json`, allowing the app to interact with Base networks dynamically.

### Explorer Integration
- **BaseScan** serves as the explorer for both Base Mainnet and Base Sepolia.
- This integration ensures that all on-chain data is transparent and can be traced back to the explorer, enhancing the project’s transparency.

---

## Future Considerations

1. **Base Network Expansion**:  
   As Base develops and additional networks are launched, the architecture can easily be extended to support new networks by adding configuration entries to `base.networks.json`.

2. **Transaction Simulations**:  
   Although the project is primarily focused on read-only operations, there might be room in the future for simulation of transactions or even **gasless transactions** if Base’s capabilities expand in that direction.

_Last updated: initial scaffold_
