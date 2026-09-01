# IERC20 solidity contract implementation

This repo contains a manual implementation of the Ethereum Request for Comment 20 token.

## The contract features:

   1. A "IERC20" Interface containing the minimal standart ERC20 functions and events.
   2. A "ERC20" contract that implements the IERC20 token interface plus "mint(uint256)" and "burn(uint256)" functions.

### The IERC20 Interface

This interface implements the minimal standar for ERC20 tokens, having:
   - A "Transfer(address indexed, address indexed, uint256)" event that emits the indexed address of the balance account "from", the balance account "to", and the amount of ERC20 sended "from -> to".
   - A "Approval(address indexed, address indexed, uint256)" event that emits the indexed address of the balance owner, the indexed address of the approved sender, and the amount of ERC20 approved "owner = sender".
   - An external view "totalSupply()" function returning the total supply of the ERC20 circulating token.
   - An external view "balanceOf(address)" function returning the registered address current balance of the ERC20 token.
   - An external "transfer(address, uint256)" function that transfers amount of ERC20 from one account to another returning the transaction success or not success.
   - An external view "allowance(address, address)" function returning the amount of abled ERC20 a spender can spend from a ERC20 owner.
   - An external "approve(address, uint256)" function that allows the sender to approve a spender to spend a given amount of ERC20 token owned returning the transaction success.
   - An external "transferFrom(address, address, uint256)" function that lets the sender, in which context is now the spender, to spend ERC20 tokens abled to him transfering from one account to another returning the transaction success.


### The ERC20 implementation

This implementation of IERC20 Interface acomplishes the aforementioned description of the interface. However, also implements:
   - A public string "name" state variable that holds the ERC20 token name.
   - A public string "symbol" state variable that holds the ERC20 token symbol.
   - A public uint8 "decimals" state variable that holds the ERC20 token amount of decimals (also called token divisibility).
   - A external "mint(uint256)" function that lets anyone mint a given amount of tokens to the ERC20 implementation, that will go directly to the sender balance.
   - A external "burn(uint256)" cuntion that lets anyone burn a given amount of tokens to the ERC20 implementation, that will dissapear directly from the sender balance.


## Advise:

The implementation has practice purpouses only. The balance erros, underflows and overflows are delegated directly to solidity checked math itself. This contract is merely an example of a ERC20 implementation and interface, so its not recommended nor intended to be a ready-to-copy implementation.