# Decentralized Voting System

A full-stack Web3 application for decentralized voting, built with the MERN stack and Ethereum/Polygon smart contracts.

## Project Structure

- `/smart_contracts`: Hardhat project containing the Solidity smart contracts.
- `/backend`: Node.js/Express server with MongoDB for storing off-chain metadata.
- `/frontend`: React application built with Vite, styled with modern CSS, and integrated with Web3 using ethers.js.

## Prerequisites

- Node.js (v18+)
- MongoDB (Running locally or MongoDB Atlas)
- MetaMask extension installed in your browser

---

## 1. Smart Contract Setup

1. Open a terminal and navigate to the `smart_contracts` folder:
   ```bash
   cd smart_contracts
   npm install
   ```
2. Start a local Hardhat node:
   ```bash
   npx hardhat node
   ```
   *(Keep this terminal running)*

3. Open a new terminal, navigate to `smart_contracts`, and deploy the contract to the local network:
   ```bash
   npx hardhat run scripts/deploy.js --network localhost
   ```
4. Copy the deployed contract address and update it in `frontend/src/context/Web3Context.jsx` (`contractAddress` variable).
5. Import one of the Hardhat accounts into your MetaMask (using the private key) and connect to the local Hardhat network (`http://127.0.0.1:8545`, Chain ID `1337`).

---

## 2. Backend Setup

1. Open a terminal and navigate to the `backend` folder:
   ```bash
   cd backend
   npm install
   ```
2. Create a `.env` file based on `.env.example`:
   ```bash
   PORT=5000
   MONGO_URI=mongodb://127.0.0.1:27017/voting_system
   ```
3. Start the backend server:
   ```bash
   npm run dev
   ```

---

## 3. Frontend Setup

1. Open a terminal and navigate to the `frontend` folder:
   ```bash
   cd frontend
   npm install
   ```
2. Start the Vite development server:
   ```bash
   npm run dev
   ```
3. Open your browser to the local URL provided by Vite (usually `http://localhost:5173`).

---

## Usage Guide

- **Admin Setup**: The account that deploys the smart contract automatically becomes the admin. Connect MetaMask with this account to access the **Admin Dashboard**.
- **Admin Dashboard**: 
  - Create elections.
  - Add candidates to an election (requires an Image URL/IPFS hash).
  - Start and end elections.
- **Voting**: 
  - Switch to another Hardhat account in MetaMask.
  - Click on an active election and cast your vote.
  - Note: You can only vote once per election.

Enjoy the Decentralized Voting experience!
