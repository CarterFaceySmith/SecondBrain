Walking through creating your own [[Cryptocurrency Tokens]]. 

## Creating Your Token 

### Method 1: The Easy Way (Token Generators)
```solidity
// You don't even need to see this code - platforms do it for you!
// But here's what they're doing behind the scenes:
contract MyToken is ERC20 {
    constructor() ERC20("CoolToken", "COOL") {
        _mint(msg.sender, 1000000 * 10**decimals());
    }
}
```

Popular platforms:
- OpenZeppelin Wizard
- Token Mint
- Cointool

Pros:
- Quick and easy
- No coding required
- Basic functionality guaranteed

Cons:
- Limited customisation
- Generic features
- Less learning experience

### Method 2: The Proper Way (Custom Development)

#### 1. Setting Up Your Dev Environment
```bash
# Install development tools
npm install -g truffle
npm install @openzeppelin/contracts
```

#### 2. Basic ERC-20 Token Example
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyCustomToken is ERC20 {
    constructor(uint256 initialSupply) ERC20("MyToken", "MTK") {
        _mint(msg.sender, initialSupply * 10**decimals());
    }
    
    // Add custom functions here
    function burnTokens(uint256 amount) public {
        _burn(msg.sender, amount);
    }
}
```

#### 3. Cool Features You Might Want
```solidity
// Pausable transfers
function pause() public onlyOwner {
    _pause();
}

// Mint new tokens
function mint(address to, uint256 amount) public onlyOwner {
    _mint(to, amount);
}

// Token vesting
mapping(address => uint256) private _vestingPeriods;
```

## Important Decisions 

### 1. Token Economics
- **Total Supply**: How many tokens?
  ```solidity
  uint256 private constant INITIAL_SUPPLY = 1000000 * 10**18; // 1 million tokens
  ```
- **Decimals**: Usually 18 (like [[Ethereum (ETH)]])
- **Distribution**: How will you spread them out?

### 2. Features to Consider
- Burnable (can tokens be destroyed?)
- Mintable (can more be created?)
- Pausable (can you stop transfers?)
- Access Control (who can do what?)

### 3. Security Features
```solidity
// Example of rate limiting
contract RateLimitedToken is ERC20 {
    mapping(address => uint256) private _lastTransferTime;
    uint256 private constant TRANSFER_COOLDOWN = 1 hours;

    function transfer(address to, uint256 amount) public virtual override returns (bool) {
        require(block.timestamp >= _lastTransferTime[msg.sender] + TRANSFER_COOLDOWN, "Too soon");
        _lastTransferTime[msg.sender] = block.timestamp;
        return super.transfer(to, amount);
    }
}
```

## Testing Your Token 

### Local Testing
```javascript
// test/MyToken.test.js
const MyToken = artifacts.require("MyToken");

contract("MyToken", accounts => {
    it("should put 1000000 tokens in first account", async () => {
        const token = await MyToken.deployed();
        const balance = await token.balanceOf(accounts[0]);
        assert.equal(balance.toString(), "1000000000000000000000000");
    });
});
```

### Test Networks
1. Ethereum: 
   - Goerli
   - Sepolia
2. BSC: 
   - BSC Testnet
3. Polygon: 
   - Mumbai Testnet

## Deployment 

### 1. Prepare Your Contract
```javascript
// migrations/2_deploy_token.js
const MyToken = artifacts.require("MyToken");

module.exports = function(deployer) {
    deployer.deploy(MyToken, 1000000); // Deploy with 1 million tokens
};
```

### 2. Deploy Command
```bash
truffle migrate --network goerli
```

### 3. Verify Your Contract
```bash
# Example for Etherscan
npx hardhat verify --network mainnet DEPLOYED_CONTRACT_ADDRESS "Constructor argument 1"
```

## Best Practices 

1. **Security First**
   - Always audit your code
   - Use tested libraries (OpenZeppelin)
   - Test thoroughly on testnets

2. **Documentation**
   ```solidity
   /// @notice Explains what the function does
   /// @param amount The number of tokens to burn
   /// @return success True if the burn succeeded
   ```

3. **Gas Optimization**
   ```solidity
   // Bad
   for(uint i = 0; i < array.length; i++) { ... }
   
   // Good
   uint256 length = array.length;
   for(uint i = 0; i < length; i++) { ... }
   ```

## Common Pitfalls 

1. **Not Testing Enough**
   - Test all functions
   - Test edge cases
   - Test with different accounts

2. **Poor Access Control**
   ```solidity
   // Bad
   function mint() public {
       _mint(msg.sender, 1000);
   }
   
   // Good
   function mint() public onlyOwner {
       _mint(msg.sender, 1000);
   }
   ```

3. **Forgetting Gas Costs**
   - Each function costs gas
   - Complex operations = more gas
   - Plan your functions accordingly

## Fun Extra Features 

### 1. Token Burning Events
```solidity
event TokensBurned(address indexed burner, uint256 amount);

function burn(uint256 amount) public {
    _burn(msg.sender, amount);
    emit TokensBurned(msg.sender, amount);
}
```

### 2. Token Rewards
```solidity
mapping(address => uint256) private _lastRewardTime;

function claimReward() public {
    require(block.timestamp >= _lastRewardTime[msg.sender] + 1 days, "Too soon");
    _mint(msg.sender, 100 * 10**decimals());
    _lastRewardTime[msg.sender] = block.timestamp;
}
```
