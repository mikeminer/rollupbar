# 🍸 The Rollup Bar — On-Chain Hospitality on Optimism

**The Rollup Bar** is a fully on-chain hospitality dApp built on **Optimism (Layer 2 Ethereum)**.  
Guests can claim **free NFT drinks**, send **on-chain messages**, and **tip in ETH** to speed up service — all directly from their wallet.

> “Where every round is a transaction, and every tip rolls up faster.” 🥂

---

## 🔴 Concept

This is the red-themed sibling of **Based Pasta Ristorante (Base Network)** —  
a fun crossover between Web3 and real-world service experiences.

Each guest interaction (`press`) writes a message and a tip to the smart contract,  
emitting an event that appears instantly on the live feed UI.

**Optimism Layer 2** provides the perfect bar atmosphere: fast, low fees, and high energy.

---

## ⚙️ Features

- 🧾 **On-Chain Orders** — Every drink order is stored as a blockchain transaction.  
- 🧉 **Drink NFTs** — Choose among several collectible NFT beverages.  
- 💸 **Tipping System** — Tips in ETH dynamically affect the delivery ETA.  
- 🌐 **EIP-6963 Wallet Support** — Works with MetaMask, Coinbase, Rainbow, Rabby, and more.  
- 🔴 **Optimism Network** — Fully configured for mainnet (chain ID 10).  
- ⚡ **Instant Feed** — Orders and messages stream in real time via event subscriptions.

---

## 🧩 Tech Stack

- **Frontend:** Pure HTML, CSS, and vanilla JavaScript (no framework required)  
- **Blockchain:** [Optimism Mainnet](https://optimism.io/)  
- **Library:** [ethers.js v6](https://docs.ethers.org/v6/)  
- **Wallet Support:** EIP-6963 multi-wallet discovery  
- **Smart Contract:** Minimal press event contract with `press()` and `Pressed` event

---

## 🧱 Smart Contract Overview

```solidity
event Pressed(
  address indexed user,
  uint256 totalPresses,
  uint256 userPresses,
  string message,
  uint256 tip
);

function press(string calldata message_) external payable;
function totalPresses() public view returns (uint256);
function presses(address user) public view returns (uint256);
function cooldownSeconds() public view returns (uint256);
