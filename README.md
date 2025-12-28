# Privacy-Preserving Energy Trading for Embodied Agents in Industry 5.0

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi%205-blue)](https://www.raspberrypi.com/)
[![Framework](https://img.shields.io/badge/Framework-Hyperledger%20Besu-green)](https://www.hyperledger.org/use/besu)

> **Official Implementation** of the paper: *Privacy-Preserving Energy Trading for Embodied Agents in Industry 5.0: An Authority-Free ZK-Proof Scheme with Dual-Chain Architecture*.

Submitted to **IEEE Transactions on Industrial Informatics (TII)**.

## 🏗 System Architecture
This project implements an authority-free energy trading scheme using a dual-chain architecture:
- **Service Chain (Chain A):** Handles logic verification using **Groth16 ZK-Proofs**.
- **Payment Chain (Chain B):** Handles asset settlement via an event-driven bridge.
- **Edge Device:** Optimized for **Raspberry Pi 5** (representing Mobile Embodied Agents).

## 📂 Repository Structure
- `circuits/`: ZoKrates source code for the **Geo-ZKP** circuit (Geometry fencing & Safety checks).
- `contracts/`: Solidity smart contracts for **Hyperledger Besu** (Verifier & Payment logic).
- `formal-verification/`: **ProVerif** scripts proving secrecy and atomicity (as discussed in Section IV-E).
- `hardware-benchmarks/`: Performance logs from the embedded implementation.

## ⚡ Quick Start (Formal Verification)
To reproduce the security proofs mentioned in the paper:

1. Install [ProVerif](https://bblanche.gitlab.io/proverif/).
2. Run the verification script:
   ```bash
   proverif formal-verification/protocol.pv
