# Token_Owner Smart Contract

## Overview

The Token_Owner smart contract is a simple implementation of a token system on the Ethereum blockchain. This contract allows users to mint and burn tokens, maintaining a record of token balances associated with different addresses.

## Contract Details

- *Token Name*: Sidharth
- *Token Abbreviation*: SID
- *Total Supply*: The total number of tokens currently in circulation.

## Features

1. *Minting Tokens*: Allows authorized users to create new tokens and assign them to a specified address.
2. *Burning Tokens*: Allows authorized users to destroy tokens from a specified address, reducing the total supply.

## Prerequisites

- [Solidity](https://soliditylang.org/) (version ^0.8.18)
- An Ethereum development environment (such as [Remix](https://remix.ethereum.org/), [Truffle](https://www.trufflesuite.com/), or [Hardhat](https://hardhat.org/))

## Installation and Deployment

1. *Clone the Repository* (if applicable):
    sh
    git clone <repository_url>
    cd <repository_directory>
    

2. *Open in Remix*:
    - Navigate to [Remix](https://remix.ethereum.org/).
    - Create a new file and copy the contract code into it.
    - Compile the contract using the Solidity compiler version ^0.8.18.
    - Deploy the contract on the desired network (e.g., Ethereum Mainnet, Ropsten Testnet, or a local development network).

## Contract Code

solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Token_Owner {
    string public token_name = "Sidharth";
    string public token_abbr = "sid";
    uint public total_sum = 0;

    mapping (address => uint) public balances;

    function mint(address add, uint val) public {
        total_sum += val;
        balances[add] += val;
    }

    function burn(address add, uint val) public {
        if (total_sum < val || balances[add] < val) {
            // Do nothing if the conditions are not met
        } else {
            total_sum -= val;
            balances[add] -= val;
        }
    }
}


## Functions

### mint(address add, uint val)

*Description*: Mints new tokens and assigns them to the specified address.

*Parameters*:
- add: The address to which the tokens will be assigned.
- val: The number of tokens to mint.

*Behavior*:
- Increases the total_sum by val.
- Increases the balance of add by val.

### burn(address add, uint val)

*Description*: Burns tokens from the specified address, reducing the total supply.

*Parameters*:
- add: The address from which the tokens will be burned.
- val: The number of tokens to burn.

*Behavior*:
- Decreases the total_sum by val if the conditions are met.
- Decreases the balance of add by val if the conditions are met.

*Conditions*:
- The total_sum must be greater than or equal to val.
- The balance of add must be greater than or equal to val.

## Usage

1. *Minting Tokens*:
   - Call the mint function with the desired address and the number of tokens to mint.
     sh
     mint(0xYourAddress, 100);
     

2. *Burning Tokens*:
   - Call the burn function with the desired address and the number of tokens to burn.
     sh
     burn(0xYourAddress, 50);
     

## License

This contract is licensed under the MIT License. SPDX-License-Identifier: MIT.

## Contributing

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes.
4. Submit a pull request.

## Author

Sidharth Gupta

## UID 

21bcs11398
