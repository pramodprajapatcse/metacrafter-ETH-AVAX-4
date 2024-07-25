
# Degen_Gaming

A smart contract for managing a gaming token system with redeemable NFT rewards.

## Description

The `Degen_Gaming` contract allows the minting, transferring, and burning of a custom ERC-20-like token called "Degen" (symbol: DGN). The contract also enables users to redeem tokens for specific NFT rewards. This project is designed for gaming ecosystems where users can earn, transfer, and redeem tokens for in-game items.

## Getting Started

### Prerequisites

To deploy and interact with this contract, you need:

- [Solidity](https://docs.soliditylang.org/en/v0.8.26/installing-solidity.html) ^0.8.26
- [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/)
- [Truffle](https://www.trufflesuite.com/truffle) or [Hardhat](https://hardhat.org/) for smart contract development
- [MetaMask](https://metamask.io/) for managing Ethereum accounts

### Installing

1. Clone the repository:

    ```sh
    git clone https://github.com/yourusername/degen_gaming.git
    cd degen_gaming
    ```

2. Install dependencies (if applicable):

    ```sh
    npm install
    ```

### Executing program

1. Compile the contract:

    ```sh
    truffle compile
    # or
    npx hardhat compile
    ```

2. Deploy the contract:

    ```sh
    truffle migrate
    # or
    npx hardhat run scripts/deploy.js
    ```

3. Interact with the contract using a script or via a console:

    ```sh
    truffle console
    # or
    npx hardhat console
    ```

4. Example commands:

    ```js
    const DegenGaming = artifacts.require("Degen_Gaming");
    let instance = await DegenGaming.deployed();

    // Mint tokens
    await instance.mint(100, '0xYourAddress', { from: '0xHeadquartersAddress' });

    // Transfer tokens
    await instance.transfer(50, '0xReceiverAddress', { from: '0xYourAddress' });

    // Redeem rewards
    let reward = await instance.redeem(1, { from: '0xYourAddress' });
    console.log(reward);
    ```

## Functions

### `mint(uint amount, address receiver_address)`

Mints new tokens to the specified address. Only callable by the contract owner.

### `transfer(uint amount, address receiver_address)`

Transfers tokens from the sender's balance to the specified address.

### `burn(uint amount)`

Burns (destroys) tokens from the sender's balance.

### `Check_Balance(address user_address)`

Returns the token balance of the specified address.

### `redeem(uint reward_ID)`

Redeems tokens for a specific NFT reward. Returns the name of the redeemed reward.

### `getRedeemedItems(address user)`

Returns an array of redeemed items for the specified address.

## Help

For common problems or issues:

1. Ensure you have the correct version of Solidity installed.
2. Make sure your Ethereum client is running and properly configured.
3. Check the contract address and ensure it's correctly deployed.

```sh
truffle console
# or
npx hardhat console
```

## Authors

- Pramod Prajapat - [Your Contact Information](https://twitter.com/pramodprajapat)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
