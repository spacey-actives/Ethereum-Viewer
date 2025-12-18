# Ethereum Viewer

Ethereum Viewer is a web application that allows users to connect to Ethereum wallets, check Ethereum blockchain data, and monitor account balances in real-time. It is designed as a lightweight and user-friendly tool for interacting with Ethereum networks like Base.

---

## Base ecosystem alignment

Built for Base.

Supported networks:
- Base Mainnet  
  chainId (decimal): 8453  
  Explorer: https://basescan.org  

- Base Sepolia  
  chainId (decimal): 84532  
  Explorer: https://sepolia.basescan.org  

The application targets Base networks explicitly and uses official Ethereum and Base RPC endpoints.

---

## What the script does

The app.eth-viewer.ts script provides an in-browser interface that:

1) Connects a wallet using Coinbase Wallet SDK  
2) Reads and validates the active chainId  
3) Performs read-only Ethereum RPC queries:
   - Latest block number  
   - ETH balance of the connected address  
4) Fetches block details (timestamp, gas usage)  
5) Allows ETH balance checks for arbitrary addresses  
6) Outputs Basescan links for verification  

All interactions are strictly read-only. No transactions are broadcast.

---

## Repository structure

- app.eth-viewer.ts  
  Browser-based script that connects to a wallet, toggles Ethereum networks, and inspects onchain state.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - ERC721.sol — smart contract that implements the ERC-20 token standard
  - ERC20.sol — smart contract that implements the ERC-721 token standard
  

- package.json  
  Dependency manifest including Coinbase SDKs and 2–5 repositories from the Base GitHub organization.

- README.md  
  Technical documentation, Base references, licensing, and testnet deployment records.

---

## Libraries used

- @coinbase/wallet-sdk  
  Wallet connection layer compatible with Coinbase tooling and Ethereum accounts.

- viem  
  RPC client used for Ethereum and Base reads and block inspection.

- Coinbase GitHub repositories  
  Included as dependencies to reference the broader Coinbase open-source ecosystem.

- Base GitHub repositories  
  Included as dependencies to document linkage with Base tooling and infrastructure.

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with a modern frontend dev server and open the page in a browser.

Expected result:
- Connected address printed with Basescan link  
- Active chainId displayed (8453 or 84532)  
- Read-only Ethereum RPC data displayed  
- Block data available on demand  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author

GitHub: https://github.com/spacey-actives

Email: spacey_actives.0r@icloud.com

Public contact: https://x.com/Fernand22313282

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract ERC721.sol address:  
0xba57b530537489278df18aab240cac794a697f01 

Deployment and verification:
- https://sepolia.basescan.org/address/0xba57b530537489278df18aab240cac794a697f01 
- https://sepolia.basescan.org/0xba57b530537489278df18aab240cac794a697f01/0#code  

Contract ERC20.sol address:  
0x05cf6f644ebb003db6cbf192a7076dda96ce94b8

Deployment and verification:
- https://sepolia.basescan.org/address/0x05cf6f644ebb003db6cbf192a7076dda96ce94b8
- https://sepolia.basescan.org/0x05cf6f644ebb003db6cbf192a7076dda96ce94b8/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.

