# MyToken
My project focuses on creating tokens in order to manage and keep my unique token's data.

## Description
In my token generation project, I first established a contract that stores the details of my token, such as the token name, abbr., and total supply. I had made these variables public.

The second step is to define a mapping variable that checks how many tokens each address has. The keys for the mapping are Ethereum addresses. The values are unsigned integers representing the token balance associated with each address.

The third step is to construct a mint function that allows fresh tokens to be added to the specified address. The parameters are _value and _address. Increases the total supply by the _value, as does the balance of the _to address. This function was made public for the sake of simplicity.

The fourth step is to develop another function called burn function. This method has the opposing functionality of the mint function in that it destroys tokens with a certain value from the provided address. functions Determines if the balance of the _from address is more than or equal to the _value to be burnt. If there is a sufficient balance, it reduces the totalSupply by _value and the _from address balance by _value. The burn function has a critical check to prevent errors: Before burning tokens, it ensures that the address starting the burn (_from) has sufficient tokens to cover the amount being burnt. This eliminates unintentional overburning and helps to keep the token supply stable.

### Getting Started
### Executing program
To execute this program, utilise Remix, an online Solidity IDE. To get started, visit the Remix website at https://remix.ethereum.org. Once on the Remix website, click the "+" icon in the left-hand sidebar to create a new file. Save the file with a.sol extension (such as MyToken.sol). Copy and paste the code below into the file.

// SPDX-License-Identifier: MIT pragma solidity 0.8.18; contract myToken {

string public tokenName = "ALPHA";
string public tokenAbbrv = "BETA";
uint public totSupply = 0; 

mapping(address => uint) public balances;

function mint(uint _value, address _address) public {
    totSupply += _value;
    balances[_address] += _value;
}

function burn(uint _value, address _address) public {
    if (balances[_address] >= _value){
        totSupply -= _value;
        balances[_address] -= _value;
    }
}
}

 ####  Help
To compile the code, select the "Solidity Compiler" tab from the left-hand sidebar. Make sure the "Compiler" option is selected to "0.8.18" (or a compatible version), then click the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Mytoken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint, burn function or check balance. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" or "burn" function. Finally, click on the "transact" button to execute the function and retrieve the token you burned or minted.

 #####  Authors
UJJAWAL PARMAR
