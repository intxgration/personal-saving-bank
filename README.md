# Personal Savings Bank (Smart Contract)

##  Overview
The Personal Savings Bankis a Solidity smart contract that acts as a private digital vault for storing and managing Ether (ETH).  
It allows anyone to deposit ETH, while only the contract owner (the deployer) can withdraw funds.  

This project demonstrates basic smart contract functionality including deposits, withdrawals, access control, and balance checks.



##  Features
- Deposit ETH: Any user can send ETH to the contract using the `deposit()` function.
- Check Balance: Anyone can view the total ETH stored in the contract using `getBalance()`.
- Withdraw ETH: Only the contract owner can withdraw ETH using `withdraw(uint _amount)`.
- Safety Filter: The contract ensures the owner cannot withdraw more than the available balance using `require`.



##  Smart Contract Functions

### `deposit()`
- Type: `public payable`
- Description: Allows any user to send ETH to the contract.
- **Usage**: Call `deposit()` and attach ETH in the transaction.

### `getBalance()`
- Type: `public view returns (uint)`
- Description: Returns the current ETH balance stored in the contract.
- Usage: Call `getBalance()` to check how much ETH is stored.

### `withdraw(uint _amount)`
- Type: `public`
- Description: Allows only the contract owner to withdraw a specified amount of ETH.
- Safety Checks:
  - Ensures caller is the owner.
  - Ensures requested amount does not exceed contract balance.
- Usage: Call `withdraw(amount)` with the desired withdrawal amount.



## 2. Deploy the Contract**  
   Deploy the contract to your preferred Ethereum network (e.g., local Ganache, testnet, or mainnet).  
   The deployer’s address becomes the owner.

3. Deposit ETH
   - Any user can call `deposit()` and send ETH.  
   - Example: In Remix, select `deposit()` and enter ETH in the "Value" field.

4. Check Balance  
   - Call `getBalance()` to see the total ETH stored.

5. **Withdraw ETH**  
   - Only the owner can call `withdraw(amount)`.  
   - Example: `withdraw(1000000000000000000)` withdraws **1 ETH**.



##  Example Workflow
1. Alice deploys the contract → Alice is the **owner**.  
2. Bob deposits 2 ETH → Contract balance = 2 ETH.  
3. Alice deposits 1 ETH → Contract balance = 3 ETH.  
4. Alice calls `withdraw(1 ETH)` → Contract balance = 2 ETH.  
5. Bob tries to withdraw → Transaction fails (not the owner).  



##  Security Notes
- Only the owner can withdraw funds.  
- Withdrawals are restricted to the available balance.  
- ETH transfers use `transfer()` to ensure safe execution.  



##  License
This project is licensed under the MIT License.  
You are free to use, modify, and distribute this code with proper attribution.
