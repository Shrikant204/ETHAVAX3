# CreateMintTokenProject

Project ETH + AVAX Module 3: Create and Mint Token

## Description

This is a simple Ethereum ERC-20 token smart contract written in Solidity. The contract allows the owner to mint new tokens, burn their own tokens, and transfer tokens to other addresses.

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., CreateMintTokenProject.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20{
    address public Owner;
    constructor() ERC20("ANDREToken", "DRE") {
        Owner =msg.sender;
        _mint(msg.sender, 10000);
    }

    function mint(address to, uint256 amount) public {
        require(msg.sender == Owner, "Only the owner can MINT TOKENS");
        _mint(to, amount);
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }

    function transfer(address to, uint256 amount) public override returns (bool) {
        _transfer(_msgSender(), to, amount);
        return true;
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile CreateMintTokenProject.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "CreateMintTokenProject" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can use all the functions in the contract first on the left-hand sidebar, you can interact with it by clicking the different variables to see different information about the created token. As per the needed in the modules you can also mint, burn, and transfer tokens, simply select the appropriate accounts when executing these functions to avoid errors.

## Authors

Andre Martee Valerio
[@Dr_EanValerio](https://twitter.com/Dr_EanValerio)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
