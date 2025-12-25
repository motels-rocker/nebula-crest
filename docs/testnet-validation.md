# Nebula Crest — Testnet Validation Process

This document outlines the validation steps for contracts deployed on **Base Sepolia** during testnet phases.

---

## Initial Setup for Validation

### Network: **Base Sepolia**  
### Chain ID: **84532**  
### RPC Endpoint: **https://sepolia.base.org**  
### Explorer: **https://sepolia.basescan.org**

Before beginning validation, ensure that the project is correctly configured for Base Sepolia by referencing the `config/base.networks.json` file. Verify that **Base Sepolia** is selected as the active network and that all RPC endpoints are correctly set.

---

## Validation Steps

### Step 1 — Verify Configuration
- [ ] Confirm `chainId` is set to **84532** (Base Sepolia).
- [ ] Ensure the correct RPC URL (`https://sepolia.base.org`) is in use.
- [ ] Check that `rpcTimeoutMs` is set to 10000ms for network reliability.

### Step 2 — Test RPC Connectivity
- [ ] Fetch the latest block number and verify it is greater than `0`.
- [ ] Retry fetching after a short delay and confirm block number advances.
- [ ] Test fallback RPC URL by switching to `https://base-sepolia-rpc.publicnode.com` if the default fails.

### Step 3 — Read-only Probes
Use the **sample addresses** from `scripts/sample-addresses.json` for consistency across validation.

- [ ] Get ETH balance for `exampleEOA` and ensure it returns a valid, non-zero value.
- [ ] Ensure that `exampleContract` is deployed and can return its code (use the `getCode` function).
- [ ] Check that `zero` address returns zero balance and that `burn` address does not cause errors.

### Step 4 — Explorer Verification
- [ ] Open the `exampleEOA` in the **BaseScan Sepolia** explorer and verify that it matches the expected results.
- [ ] Check the block number in the explorer to ensure it matches the current chain state.
- [ ] Ensure no references to **Base Mainnet** are displayed during Sepolia testing.

---

## Final Gate

Before moving to **Base Mainnet**:
- [ ] Ensure all testnet checks pass successfully.
- [ ] Confirm that no hardcoded values are used for networks (all should come from `base.networks.json`).
- [ ] Make sure that **Base Sepolia** explorer links and transaction hashes are properly resolving.

_Last updated: initial scaffold_
