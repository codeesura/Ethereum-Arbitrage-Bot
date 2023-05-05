# Ethereum Arbitrage Bot

This repository contains a smart contract for a simple Ethereum-based arbitrage bot that takes advantage of price differences between Uniswap and Sushiswap decentralized exchanges. The contract is written in Solidity and uses the UniswapV2 and SushiSwap Router interfaces.

## Table of Contents
- [Overview](#overview)
- [Smart Contract Description](#smart-contract-description)
- [Setup](#setup)
- [Deploying the Contract](#deploying-the-contract)
- [Interacting with the Contract](#interacting-with-the-contract)
- [Disclaimer](#disclaimer)

## Overview

Arbitrage is the process of taking advantage of price differences between markets, in this case, decentralized exchanges (DEXs). This contract automates the process of buying tokens on one DEX and selling them on another to profit from the price difference.

## Smart Contract Description

The smart contract `MyContract` performs the following steps:

1. Receives an amount of Wrapped Ether (WETH) from the user.
2. Buys UNI tokens on Uniswap using the received WETH.
3. Sells the UNI tokens on Sushiswap and receives WETH.
4. Sends the profit back to the user.

The contract uses the following interfaces:

- IUniswapV2Router: The interface for interacting with the Uniswap V2 router contract.
- ISushiSwapRouter: The interface for interacting with the SushiSwap router contract.
- IWETH9: The interface for interacting with the Wrapped Ether (WETH) contract.

## Setup

1. Install [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/).
2. Install [Truffle](https://www.trufflesuite.com/) and [Ganache](https://www.trufflesuite.com/ganache) for local development.
3. Clone this repository.
4. Install dependencies:

```bash
npm install
```

5. Configure Truffle by editing the `truffle-config.js` file.

## Deploying the Contract

1. Start Ganache.
2. Compile the smart contract:

```bash
truffle compile
```

3. Deploy the smart contract to the local development network:

```bash
truffle migrate --network development
```


## Interacting with the Contract

Use Truffle console or a web3 library like [web3.js](https://github.com/ethereum/web3.js/) or [ethers.js](https://github.com/ethers-io/ethers.js/) to interact with the deployed contract.

Example using Truffle console:

1. Start the Truffle console:

```bash
truffle console --network development
```
2. Get an instance of the deployed contract:

```bash
let myContract = await MyContract.deployed()
```

3. Call the `swap` function with the desired amount of WETH:

```bash
await myContract.swap(web3.utils.toWei("1", "ether"), {from: accounts[0]})
```

## Using Remix IDE

You can also use Remix IDE, a web-based development environment for writing, testing, and deploying Solidity smart contracts, to work with this arbitrage bot contract.

### Setup

1. Visit [Remix IDE](https://remix.ethereum.org/).
2. Click the "Solidity" environment button.
3. Create a new file by clicking the "+" icon and name it `MyContract.sol`.
4. Copy the content of the provided smart contract and paste it into `MyContract.sol`.
5. In the left sidebar, go to the "Solidity Compiler" tab and compile the smart contract.

### Deploying the Contract

1. In the left sidebar, go to the "Deploy & Run Transactions" tab.
2. Select the appropriate environment, such as "Injected Web3" for MetaMask or "JavaScript VM" for a simulated environment.
3. If using MetaMask, connect your wallet and choose the appropriate account.
4. Click the "Deploy" button to deploy the smart contract.

### Interacting with the Contract

Once the contract is deployed, you can interact with it using the "Deployed Contracts" section in the "Deploy & Run Transactions" tab.

1. Expand the deployed contract by clicking on the arrow next to its address.
2. Use the provided input fields and buttons to call the functions of the contract. For example, call the `swap` function and provide the amount of WETH you want to use for the arbitrage.


## Disclaimer

This project is for educational purposes only. Arbitrage opportunities are not guaranteed and can be highly volatile. The author is not responsible for any financial losses incurred from using this code. Use at your own risk.
