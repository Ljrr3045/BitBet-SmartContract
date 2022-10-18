# Solidity API

## RandomNumber

### keyHash

```solidity
bytes32 keyHash
```

### lastRequestId

```solidity
bytes32 lastRequestId
```

### fee

```solidity
uint256 fee
```

### randomResult

```solidity
uint256 randomResult
```

### until

```solidity
uint256 until
```

### constructor

```solidity
constructor(address vrfCoordinator) public
```

The address of the VRF Coordinator contract must be supplied, depending on the blocksChain in which we are.

_For both the keyHash and Fee variables, their value will be variable as long as different strings are used._

### getRandomNumber

```solidity
function getRandomNumber() public returns (bytes32 requestId)
```

This function allows you to request a random number

_For this function to work, you must previously supply this contract with Link Token, to cover 
the corresponding fees. This function can only be called by the owner of the contract._

### fulfillRandomness

```solidity
function fulfillRandomness(bytes32 requestId, uint256 randomness) internal
```

_Internal function overridden to set the variable randomResult._

### setUntil

```solidity
function setUntil(uint256 _until) public
```

This function allows you to set the variable until, this variable will be used to delimit the range of 
numbers in which you want to obtain the random number, ex: 1 to 50.

_This function can only be called by the owner of the contract._

## VRFCoordinator

### constructor

```solidity
constructor(address linkAddress) public
```
