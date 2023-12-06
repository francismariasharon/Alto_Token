# Alto_Token

I have used openzeppelin contract library to import all my functions to mint, burn, transfer, approve, transfer ownership, etc. This is possible by creating a token.

## Description

Alto is an ERC-20 token that implements burning functionality and is owned by an address specified during deployment. It utilizes the Ownable contract from OpenZeppelin, ensuring that only the specified owner address has control over some functions, such as minting new tokens. New tokens can be minted by the owner using the mint function. Only the owner has the privilege to mint additional tokens.
The contract can be deployed by specifying the initial owner address. The deployment script initializes the token with the name "Alto" and the symbol "ALT."

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Alto.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Alto is ERC20, ERC20Burnable, Ownable {
    constructor(address initialOwner) ERC20("Alto", "ALT") Ownable(initialOwner) {}

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
}
//Burn function is imported from openzeppelin

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.20" (or another compatible version), and then click on the "Compile Alto.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Alto" contract from the dropdown menu, and then click on the "Deploy" button.


## Authors

Francis MS

@francismariasharon@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
