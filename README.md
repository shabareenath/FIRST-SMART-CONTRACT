# Inbox Smart Contract Project

## Overview
This project demonstrates how to deploy and interact with a basic smart contract on the Ethereum blockchain using Solidity, Web3.js, Infura, and Mocha for testing. The project follows a structured development approach with separate files for the contract, compilation, deployment, and testing.

## Technologies & Libraries Used
### 1. **Solidity (Version: 0.8.19)**
   - The language used to write smart contracts that run on the Ethereum Virtual Machine (EVM).
   - In this project, the `Inbox` contract allows setting and getting a message.

### 2. **Web3.js**
   - A JavaScript library used to interact with Ethereum blockchain nodes via HTTP or WebSocket connections.
   - **Purpose**: Used to deploy the contract, interact with it, and manage accounts. Web3 abstracts away the low-level JSON-RPC communication.

### 3. **Infura**
   - Provides Ethereum and IPFS infrastructure.
   - **Purpose**: It is used to connect to the Sepolia test network without needing to run a local Ethereum node.

### 4. **HDWalletProvider**
   - A provider engine that handles managing a mnemonic, signing transactions, and providing a connection to the blockchain via Infura.
   - **Purpose**: It allows you to sign and send transactions with your private key/mnemonic.

### 5. **Mocha**
   - A JavaScript testing framework for Node.js.
   - **Purpose**: Used to write and execute tests for the smart contract using Chai and Web3.

### 6. **Solc**
   - Solidity compiler.
   - **Purpose**: Compiles the Solidity code and generates ABI and bytecode, which are essential for deploying the contract.

---

## Files Overview

### 1. **Inbox.sol**
   - This is the smart contract written in Solidity. It allows users to set and retrieve a string message.
   - The contract has a constructor that initializes the `message`, a public function to set the message, and a state variable `message` to store it.

### 2. **compile.js**
   - This file compiles the `Inbox` contract using the Solidity compiler (`solc`). It reads the contract, compiles it, and exports the ABI and bytecode for deployment.

### 3. **deploy.js**
   - This file handles deploying the compiled contract to the Sepolia test network using Infura and HDWalletProvider.
   - It first gets an account (using HDWalletProvider) and then deploys the contract using Web3.
   - The deployment function is asynchronous since the deployment process involves network interactions.

### 4. **inbox.test.js**
   - This file uses Mocha to test the functionality of the smart contract.
   - It checks if the contract deploys successfully and tests the `setMessage` and `message` functions.

---

## How to Run the Project

1. **Clone the repository**.
2. **Install dependencies**: Run `npm install`.
3. **Compile the contract**: Run `node compile.js`.
4. **Deploy the contract**:
   - Update the mnemonic and Infura endpoint in `deploy.js`.
   - Run `node deploy.js`.
5. **Run Tests**: 
   - Run `npm install mocha -g`.
   - Execute `npx mocha`.

---

## Conclusion
This project demonstrates how to build, deploy, and test a simple Ethereum smart contract using various technologies such as Solidity, Web3.js, Infura, and Mocha. Each part of the project serves to interact with the blockchain in a structured and programmatic way.
