

A smart contract is a protocol deployed on Blockchain which will work as long as its parameters implemented are met. 
```
contract Agreement {
address recipient;
bool conditionIsMet;

  function payout() external {
    if(conditionIsMet) {
      sendValue(recipient);
    }
  }
// ...
}
```

## Deploying a Contract
1  compile solidity to bytecodes

2  send a transaction containing the bytecode to an EVM (Ethereum Virtual Machine) node

3  the node calculates an address for your new contract

## Contract Deployment

1  The contract is passed in a solidity compiler transforming it into bytecode

2  The bytecode of the contract (protocol written), is pushed in a transaction 
    Specifying no recipient's address in the "to: "...", data: "0x6060..."" field, means to Ethereum that it needs to consider it as a smart contract
    
3  EVM node reads the transaction, and adapt the deployment on the blockchain according to the parameters completed or not in the to & data fields.

4  Smart contract is deployed on the chain

### Opcodes table (EVM)
| Opcode  | Name | Description | Gas |
| ------------- | ------------- | ------------- | ------------- |
| 0x00  | STOP  | Halts execution | 0 |
| 0x01  | ADD  | Addition operation | 3 |
| 0x02  | MUL  | Multiplication operation | 5 |
| 0x03 | SUB  | Substraction operation | 3 |

https://ethereum.org/en/developers/docs/evm/opcodes/

### Key Takeaways
-  Contracts are compiled to create bytecode
-  The **data** field contains your creation bytecode
-  the **to** field is left blank to deploy a contract
-  Your contract will have an address, balance and runtime bytecode

#### Transaction Structure (Smart Contract deployment intention)
| to | from | data |
| ------------- | ------------- | ------------- |
| no mention (specifies intention to smart contract consideration) | contract's address creator  | bytecode of smart contract | 
