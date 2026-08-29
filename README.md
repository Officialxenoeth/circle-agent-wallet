# Circle Agent Wallet — Arc Testnet

This repository contains the setup and execution workflow for a Circle Developer-Controlled Agent Wallet operating on the Arc Testnet (`ARC-TESTNET`).

## Testnet Details & Proof of Work
- **Wallet Address:** `0x39d2b07d0f508db5723d245df210cef77c1527bb`
- **Network:** Arc Testnet (`ARC-TESTNET`)
- **Tokens Interacted:** USDC, EURC

## Executed Workflow
The agent executes automated token swaps on Arc Testnet via the Circle CLI:
- `circle wallet swap EURC 2 USDC 1.9 --address 0x39d2b07d0f508db5723d245df210cef77c1527bb --chain ARC-TESTNET`
- `circle wallet swap USDC 2 EURC 1.9 --address 0x39d2b07d0f508db5723d245df210cef77c1527bb --chain ARC-TESTNET`

## Execution Steps
1. Configure Circle API credentials.
2. Initialize developer-controlled wallet on Arc Testnet.
3. Perform testnet token swaps between USDC and EURC.

## Known Testnet Issues & Bug Reports

### Issue: Stablecoin Service `createSwap` Route Failure
- **Command Executed:**
  `circle wallet swap USDC 10 EURC 9.5 --address 0x39d2b07d0f508db5723d245df210cef77c1527bb --chain ARC-TESTNET`
- **Error Output:**
  `Error: Failed to prepare swap: Stablecoin Service createSwap failed: No route found that satisfies the requested stop limit. Try increasing slippageBps or adjusting stopLimit.`
- **Impact:** High slippage or insufficient liquidity in the `ARC-TESTNET` DEX pool prevents standard swap routing above 2 USDC trades.
