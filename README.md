# Contract MyToken
This program is a simple solidity the MyToken program , to store the details of MyToken and to manage it. You can manage and update the token .

## Description
This Solidity contract MyToken store the details of MyToken -
-**Token Name:** ALPHA
-**Abbreviation:** BETA
-**Total Supply:** 0

It also contains function like - 
**Mint function**
**Burn Function** 

### Getting Started
In my token generation project-

In this, first i created the contract MyToken which stores the details of the MyToken , eg. Token name , Token Abbreviation , and total supply which is zero, and these variables are public.

### Executing program
To run this , utilise Remix, an online Solidity IDE. To get started, visit the Remix website at https://remix.ethereum.org. Once on the Remix website, click the "+" icon in the left-hand sidebar to create a new file.

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "ALPHA";
    string public tokenAbbrv = "BETA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        } else {
            // Add your desired error handling here, like reverting the transaction
        }
       }
     }

     
    


 ####  Help
To compile the code, select the "Solidity Compiler" tab from the left-hand sidebar. Make sure the "Compiler" option is selected to "0.8.18" (or a compatible version), then click the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Mytoken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint, burn function or check balance. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" or "burn" function. Finally, click on the "transact" button to execute the function and retrieve the token you burned or minted.

 #####  Authors
UJJAWAL PARMAR
