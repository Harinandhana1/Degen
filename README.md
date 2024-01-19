# Token Contract 

## Overview

This Solidity smart contract represents a basic ERC-20 token named "Degen" with additional functionalities for redeeming and purchasing vehicles. The contract allows users to mint, burn, transfer tokens, and redeem or purchase vehicles using the tokens.

## ERC-20 Token Features

### Minting Tokens

The contract owner can mint tokens to a specified account using the `mintTokens` function.

```solidity
function mintTokens(address account, uint256 amount) public onlyOwner
```

### Burning Tokens

Token holders can burn their tokens using the `burnTokens` function.

```solidity
function burnTokens(uint256 amount) public
```

### Transferring Tokens

Token holders can transfer tokens to another address using the `transferTokens` function.

```solidity
function transferTokens(address recipient, uint256 amount) external
```

## Vehicle Redemption and Purchase

### Vehicle Redemption

Users can redeem vehicles by providing the vehicle type and the desired quantity. The corresponding tokens are deducted, and the vehicle inventory is updated accordingly.

```solidity
function redeemVehicle(string memory vehicleType, uint256 quantity) external
```

### Vehicle Purchase

Users can purchase vehicles using tokens. The vehicle inventory is updated, and a log event is emitted.

```solidity
function purchaseVehicle(string memory vehicleType) external
```

## Vehicle Information

The contract maintains information about vehicle prices and inventories.

- Vehicle Prices: `vehiclePrices` mapping
- Vehicle Inventories: `vehicleInventories` mapping

## Deployment

The contract is deployed with initial token balances for the owner, vehicle prices, and inventories.

## Events

- `LogMessage`: Emitted for general logging purposes.
- `VehiclesRedeemed`: Emitted when a user purchases a vehicle
