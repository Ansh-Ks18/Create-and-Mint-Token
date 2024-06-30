# 🌟 MyToken - A Custom ERC20 Token

![ERC20](https://img.shields.io/badge/ERC20-Token-blue.svg) ![Solidity](https://img.shields.io/badge/Solidity-0.8.0-green.svg) ![OpenZeppelin](https://img.shields.io/badge/OpenZeppelin-ERC20-yellow.svg) ![Ethereum](https://img.shields.io/badge/Ethereum-Network-orange.svg)

## 🚀 Simple Overview

**MyToken** is a custom ERC20 token built on the Ethereum blockchain. It demonstrates basic functionalities of ERC20 tokens, including minting, burning, and transferring tokens. The primary use of MyToken is to serve as a learning tool for understanding ERC20 token standards and smart contract development in Solidity.

## 📜 Description

**MyToken** is designed to provide a simple yet comprehensive example of an ERC20 token. This project includes essential features such as minting new tokens, burning existing tokens, and transferring tokens between accounts. By using OpenZeppelin's ERC20 implementation, this project ensures security and adherence to best practices. MyToken is suitable for:

- Developers looking to learn about ERC20 tokens
- Students exploring blockchain technology
- Educators needing a practical example for teaching Solidity programming

## 🛠️ Getting Started

### 🚚 Installing

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Ansh-Ks18/Create-and-Mint-Token.git
   ```

2. **Open the Project in Remix**
   - Navigate to [Remix IDE](https://remix.ethereum.org/).
   - Click on the "File Explorers" icon on the left sidebar.
   - Select "Load from Filesystem" and choose the `ERC20_token` folder you cloned.

### 🛠️ Deploying the Contract Using Remix

1. **Compile the Smart Contract**
   - Open the `ERC20_token.sol` file from the file explorer.
   - Click on the "Solidity Compiler" icon on the left sidebar.
   - Ensure the compiler version is set to `0.8.0` (or compatible).
   - Click the "Compile MyToken.sol" button.

2. **Deploy the Smart Contract**
   - Click on the "Deploy & Run Transactions" icon on the left sidebar.
   - Ensure the environment is set to "Injected Web3" if you are using MetaMask or "Remix VM (London)" for a local deployment.
   - Click the "Deploy" button next to `ERC20_token` under the "Deployed Contracts" section.

3. **Interact with the Smart Contract**
   - Once deployed, you can interact with the contract using the provided UI in Remix.
   - Use the `mint`, `burn`, and `transfer` functions to test the token functionalities.

## 🆘 Help

If you encounter any issues, consider the following common solutions:

- Ensure you have the correct version of the Solidity compiler.
- Verify your network configuration in MetaMask or Remix.
- Make sure your Ethereum client (e.g., MetaMask, Ganache) is running and connected.

For further assistance, refer to the [Remix Documentation](https://remix-ide.readthedocs.io/en/latest/).

## 👨‍💻 Authors

- **ANSHU KUMAR** - [@Anshu_Kumar](https://github.com/Ansh-Ks18)

## 📄 License

This project is licensed under the MIT License - see the LICENSE.md file for details.

---

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. 
Save the file with a .sol extension (e.g.,ERC20_token.sol). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    address public owner;

    constructor(string memory name_, string memory symbol_) ERC20(name_, symbol_) {
        owner = msg.sender;
        _mint(msg.sender, 1000 * 10 ** decimals());
    }

    function mint(address to, uint256 amount) public {
        require(msg.sender == owner, "Only the contract owner can mint");
        _mint(to, amount);
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }

    function transfer(address to, uint256 amount) public override returns (bool) {
        require(amount <= balanceOf(msg.sender), "Insufficient balance");
        _transfer(msg.sender, to, amount);
        return true;
    }
}
```

Feel free to customize and adjust the sections further based on specific details or additional information about your project!
