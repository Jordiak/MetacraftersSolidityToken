# Token Creation in Solidity

Solidity assessment that tries to emulate token creation and functions.

## Description

This program was created for the purposes of accomplishing the "Getting Started with Solidity" course project on Metacrafters. This program has functions for minting and burning a declared Token.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokeName = "JCOIN";
    string public tokenAbrrv = "JC";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint function. You can use one of the sample addresses given at the top of the "Deploy & Run Transactions" tab for the transactions used in this program. 

In the mint function you will have input fields for an address and value. Use one of the sample addresses mentioned previously and any value you desire.

In the burn function you will also have input fields for an address and value. Use one of the sample addresses you have minted tokens with and enter a value of tokens you want to burn. Note that the number of tokens you wants to burn cannot exceed the balance of the address chosen.

You can use the balance function the view the balance of an address by simply clicking the function.

You can also view the total supply of tokens by clicking the total supply function.
## Help

## Authors

Jordan

## License

This project is licensed under the MIT License
