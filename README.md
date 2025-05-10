# 🚗 DecentraRide - Decentralized Blockchain Carpooling Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 📌 Project Overview

DecentraRide is a modern Web3 carpooling platform that leverages blockchain technology to create a decentralized, transparent, and efficient ride-sharing ecosystem. By utilizing smart contracts for transactions and NFT-based membership tiers, we're redefining trust and security in the sharing economy.

## 📸 Platform Screenshots

<div align="center">
  <img src="https://github.com/user-attachments/assets/5769fdcb-2630-4c08-9448-f328fefbc0d9" width="45%" />
  <img src="https://github.com/user-attachments/assets/e851fe73-aeff-4e7f-b762-644a349b4319" width="45%" />
  <br/><br/>
  <img src="https://github.com/user-attachments/assets/989cbad9-38f1-431d-b997-ae414b8230c0" width="45%" />
  <img src="https://github.com/user-attachments/assets/130b0fc0-e83f-48b0-9304-bee5545f0b38" width="45%" />
  <br/><br/>
  <img src="https://github.com/user-attachments/assets/6afb1ec6-051f-4dd6-b381-4cc4b0da1d85" width="45%" />
  <img src="https://github.com/user-attachments/assets/49154702-69b6-4f3c-bdd0-b621b0982f3c" width="45%" />
  <br/><br/>
  <img src="https://github.com/user-attachments/assets/6f04e066-eda0-427d-ae45-086750529a23" width="45%" />
  <img src="https://github.com/user-attachments/assets/3852d1d8-b598-42df-93a5-a0b62ea67bf9" width="45%" />
</div>

## 🛠️ Technology Stack

### Frontend
- **React 18** + TypeScript + Vite
- **TailwindCSS**, **shadcn/ui**, **Lucide React**
- **React Router**, **Tanstack React Query**

### Backend & Blockchain
- **Firebase**, **Ethereum/Polygon**, **Web3.js / Ethers.js**
- **Solidity** smart contracts (ERC-721), **IPFS**

## ⭐ Key Features

- 🔐 Web3 Login via MetaMask
- 🎫 NFT Membership with perks
- 🚘 Decentralized Ride Listings & Bookings
- 💵 Wallet-to-Wallet Crypto Payments (Escrow)
- 🗳️ DAO Voting & Blockchain Reputation

## 📡 API Endpoints

### Authentication

| Method | Endpoint                        | Description                                |
|--------|----------------------------------|--------------------------------------------|
| GET    | `/api/auth/nonce/:address`      | Get nonce for wallet signing               |
| POST   | `/api/auth/verify`              | Verify signed message                      |

### Rides

| Method | Endpoint                        | Description                                |
|--------|----------------------------------|--------------------------------------------|
| GET    | `/api/rides`                    | Get all available rides                    |
| GET    | `/api/rides/:id`                | Get ride details by ID                     |
| POST   | `/api/rides`                    | Post a new ride                            |
| POST   | `/api/rides/:id/book`           | Book seats on a ride                       |

### Profiles

| Method | Endpoint                        | Description                                |
|--------|----------------------------------|--------------------------------------------|
| GET    | `/api/profile/:address`         | Fetch user profile                         |
| PUT    | `/api/profile`                  | Update profile info                        |
| GET    | `/api/profile/:address/rides`   | Fetch rides for a user                     |

### Events

| Method | Endpoint                        | Description                                |
|--------|----------------------------------|--------------------------------------------|
| GET    | `/api/events`                   | List community events                      |
| GET    | `/api/events/:id`               | Event details                              |
| POST   | `/api/events/:id/register`      | Register for an event                      |

## 🔧 Smart Contracts Overview

### `RideContract.sol`

Handles ride creation, booking, escrow, and ride status.

```solidity
function createRide(...) public returns (uint256);
function bookRide(...) public payable;
function startRide(...) public onlyDriver;
function completeRide(...) public onlyDriver;
````

### `MembershipNFT.sol`

ERC-721 with tiered utility and upgrade system.

```solidity
function mintMembership(...) public payable;
function getMembershipTier(...) public view;
function upgradeNFTTier(...) public payable;
```

### `GovernanceToken.sol`

ERC-20 for DAO governance proposals and voting.

```solidity
function proposeChange(...) public returns (uint256);
function vote(...) public;
function executeProposal(...) public;
```

## 🚀 Local Setup

### Prerequisites

* Node.js v18+
* Hardhat or Ganache for local blockchain
* MetaMask for wallet integration

### Frontend Setup

```bash
git clone https://github.com/vaibhavi-2-0-2-3/poolsmart.git
cd poolsmart
npm install
npm run dev
```

### Smart Contract Deployment

```bash
npx hardhat node
npx hardhat run scripts/deploy.js --network localhost
```

### Environment Variables (`.env`)

```
VITE_FIREBASE_API_KEY=your_key
VITE_FIREBASE_AUTH_DOMAIN=your_domain
...
VITE_RIDE_CONTRACT_ADDRESS=0x...
```

## 📁 Folder Structure

```
decentra-ride/
├── public/
├── src/
│   ├── components/
│   ├── contracts/
│   ├── hooks/
│   ├── lib/
│   ├── pages/
│   └── main.tsx
├── contracts/
├── scripts/
└── hardhat.config.js
```

## 🧪 Testing

```bash
npm run test         # Frontend tests
npx hardhat test     # Smart contract tests
```

## 🚨 Known Issues

* MetaMask mobile compatibility
* Gas estimation variance
* NFT features require testnet ETH

## 🛣️ Roadmap

* [ ] Cross-chain support
* [ ] Mobile app
* [ ] Web2 rideshare APIs
* [ ] ZK-based reputation
* [ ] IoT ride tracking

## 👨‍💻 Contributing

1. Fork this repo
2. `git checkout -b feature/your-feature`
3. `git commit -m 'Add your feature'`
4. `git push origin feature/your-feature`
5. Open a PR 🚀

## 📄 License

This project is licensed under [MIT](LICENSE).

---

*For questions or support, please open an issue in the repository.*
