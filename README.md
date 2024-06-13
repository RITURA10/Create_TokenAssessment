# META Token Smart Contract

Make a unique Smart Contract that creates its own special digital coins, just like tokens. These coins can be added or removed as needed. 

# Description

This Solidity smart contract implements a simple token system named "META" with the abbreviation "MTA". The contract allows for the minting and burning of tokens, which are tracked through public variables and a mapping of addresses to balances. The total supply of tokens is dynamically managed through these operations.

# Getting Started

Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

'''

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address,uint _value) public 
    {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address,uint _value) public 
    {
        if (balances[_address] >= _value)
        {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}

'''

This Solidity smart contract, written in version 0.8.18, implements a basic token system with the name "META" and abbreviation "MTA". The contract includes the following features:

Public Variables:

tokenName: Stores the name of the token ("META").
tokenAbbrv: Stores the abbreviation of the token ("MTA").
totalSupply: Tracks the total supply of the tokens in circulation, initialized to zero.
Mapping of Balances:

balances: A mapping from addresses to their corresponding token balances (mapping(address => uint)).

Mint Function:

mint(address _address, uint _value): This function allows for minting new tokens. It takes an address and a value as parameters, increases the total supply by the given value, and adds the value to the balance of the specified address.

Burn Function:

burn(address _address, uint _value): This function enables the burning of tokens. It takes an address and a value as parameters. If the balance of the specified address is greater than or equal to the given value, it decreases the total supply by the value and deducts the value from the balance of the specified address.

The contract ensures that tokens can only be burned if the sender's balance is sufficient, preventing the destruction of more tokens than are available in the sender's balance.


# Authors

Arrow

# License 

This project is licensed under the MIT License - see the LICENSE.md file for details
