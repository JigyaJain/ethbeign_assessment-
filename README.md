# ethbeign_assessment-
This solidity eth_beginner program is a smart contract which is of creating a token. This project aims the learners to know about the concepts like functions and mapping so that they can create their own token and learn its implementation in real life blockchain.

## Description

In this program the concepts of solidity have been used to create our own token which is implemented by two functions mint and burn. By this program the reader can gain the basic understanding of solidity and learn to use function, create variable.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

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
    string public tokenName = "Jigya";
    string public tokenAbbrev = "Jig";
    string public location = "India";
    uint public totalSupply;             //default value = 0

    // mapping variable here
    mapping(address => uint) public bal;   //bal == balances

    // mint function
    function setSupply (address add, uint value) public {
        
        totalSupply += value;
        bal[add] += value;
    }

    // burn function
    function setburn (address add, uint value) public {

        if (bal[add] >= value)
        {
            totalSupply -= value;
            bal[add] -= value;
        }
    }
}


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the setMint or setBurn function which will require an address and a value. The address you can paste by copying the text under account in the same page. Finally, click on the "transact" button to execute the function. Once you transact it then call the totalSupply to check the updated value. Additionally you can call the tokenName, tokenAbbrev variables to cheeck their value.

## Authors

Jigya Jain

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
