Optimised code

```
pragma solidity ^0.8.13;

contract Store {
    uint8 index;
    bool flag1;
    bool flag2;
    bool flag3;

    uint256 number;
    address admin;
    address admin2;

    struct payments {
        bool valid;
        bool checked;
        uint8 paymentType;

        uint256 amount;
        uint256 finalAmount;
        uint256 initialAmount;
        address sender;
        address receiver;
    }

    payments[8] topPayments;
    mapping(address => uint256) balances;

    constructor() {}

    function setNumber(uint256 newNumber) public {
        number = newNumber;
    }

    function increment() public {
        number++;
    }
}

```

Foundry section

- Use Anvil to fork mainnet

https://book.getfoundry.sh/reference/anvil/

Relevant command, use your own Infura key:

```jsx
anvil --fork-url https://mainnet.infura.io/v3/$INFURA_KEY
```

Open a new Terminal window

Run a Cast command

```jsx
cast rpc eth_blockNumber --rpc-url http://localhost:8545
```

Get a response in hexadecimal
"0x10faacd”

Use Google to cast it in decimal

**17803981**
