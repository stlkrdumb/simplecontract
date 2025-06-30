# Simple Solidity Contract Example
No, additional libraries such as open zeppelin.

```sol
contract YourContractName {
    string public constant name = "Your Token Name";
    string public constant symbol = "YOURTOKENSYMBOL";
    uint8 public constant decimals = 18;
    uint256 public totalSupply = 1_000_000_000 * (10 ** uint256(decimals));
    address public owner;

    mapping(address => uint256) public balanceOf;
    mapping(address => mapping(address => uint256)) public allowance;

    event Transfer(address indexed from, address indexed to, uint256 value);
    event Approval(address indexed owner, address indexed spender, uint256 value);

    constructor() {
        owner = msg.sender;
        balanceOf[owner] = totalSupply;
        emit Transfer(address(0), owner, totalSupply);
    }
....
```

Things you should change `Your Token Name`, `YOURTOKEN SYMBOL`, and `1_000_000_000` is your token total supply.
