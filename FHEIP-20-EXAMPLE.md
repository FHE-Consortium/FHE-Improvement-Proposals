# FHEIP: Encrypted FHERC20 Token Standard

## Preamble

    FHEIP: [To be assigned]
    Title: Encrypted FHERC20 Token Standard
    Author: [Author's Name]
    Type: Standard
    Category: Token
    Status: Draft
    Created: 2023-10-04

## Simple Summary

This proposal describes an encrypted FHERC20 token standard that is inspired by OpenZeppelin's ERC20 implementation. It focuses on providing core functionalities of an ERC20 token while ensuring that transaction amounts and balances remain encrypted to enhance privacy and security.

## Abstract

The encrypted FHERC20 token standard aims to introduce a level of encryption for core functionalities including balance inquiries, transfers, and approvals. This ensures that critical transactional details such as token amounts and balances are encrypted and only accessible to authorized parties.

## Motivation

The key motivation behind this proposal is to improve user privacy and security in token transactions. Traditional ERC20 tokens expose amounts and balances on public ledgers. By encrypting these values, FHERC20 aims to prevent unauthorized access and scrutiny of transactional details.

## Specification

### Interface Definition

The encrypted FHERC20 token will implement the following interface:

```solidity
pragma solidity >=0.8.19 <0.9.0;

// SPDX-License-Identifier: MIT
// Fhenix Protocol (last updated v0.1.0) (token/FHERC20/IFHERC20.sol)
// Inspired by OpenZeppelin (https://github.com/OpenZeppelin/openzeppelin-contracts) (token/ERC20/IERC20.sol)

import { Permission, Permissioned } from "../../../access/Permissioned.sol";
import { euint128, inEuint128 } from "../../../FHE.sol";

/**
 * @dev Interface of the ERC-20 standard as defined in the ERC.
 */
interface IFHERC20 {
    /**
     * @dev Emitted when `value` tokens are moved from one account (`from`) to
     * another (`to`).
     *
     * Note that `value` may be zero.
     */
    event TransferEncrypted(address indexed from, address indexed to);

    /**
     * @dev Emitted when the allowance of a `spender` for an `owner` is set by
     * a call to {approveEncrypted}. `value` is the new allowance.
     */
    event ApprovalEncrypted(address indexed owner, address indexed spender);

    /**
     * @dev Returns the value of tokens owned by `account`, sealed and encrypted for the caller.
     */
    function balanceOfEncrypted(address account, Permission memory auth) external view returns (string memory);

    /**
     * @dev Moves a `value` amount of tokens from the caller's account to `to`.
     * Accepts the value as inEuint128, more convenient for calls from EOAs.
     *
     * Returns a boolean value indicating whether the operation succeeded.
     */
    function transferEncrypted(address to, inEuint128 calldata value) external returns (euint128);

    /**
     * @dev Moves a `value` amount of tokens from the caller's account to `to`.
     * Accepts the value as euint128, more convenient for calls from other contracts
     *
     * Returns a boolean value indicating whether the operation succeeded.
     */
    function _transferEncrypted(address to, euint128 value) external returns (euint128);

    /**
     * @dev Returns the remaining number of tokens that `spender` will be
     * allowed to spend on behalf of `owner` through {transferFrom}. This is
     * zero by default.
     *
     * This value changes when {approve} or {transferFrom} are called.
     */
    function allowanceEncrypted(address owner, address spender, Permission memory permission) external view returns (string memory);

    /**
     * @dev Sets a `value` amount of tokens as the allowance of `spender` over the
     * caller's tokens.
     *
     * Returns a boolean value indicating whether the operation succeeded.
     *
     * IMPORTANT: Beware that changing an allowance with this method brings the risk
     * that someone may use both the old and the new allowance by unfortunate
     * transaction ordering. One possible solution to mitigate this race
     * condition is to first reduce the spender's allowance to 0 and set the
     * desired value afterwards:
     * https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729
     *
     * Emits an {ApprovalEncrypted} event.
     */
    function approveEncrypted(address spender, inEuint128 calldata value) external returns (bool);

    /**
     * @dev Moves a `value` amount of tokens from `from` to `to` using the
     * allowance mechanism. `value` is then deducted from the caller's
     * allowance. Accepts the value as inEuint128, more convenient for calls from EOAs.
     *
     * Returns a boolean value indicating whether the operation succeeded.
     *
     * Emits a {TransferEncrypted} event.
     */
    function transferFromEncrypted(address from, address to, inEuint128 calldata value) external returns (euint128);

    /**
     * @dev Moves a `value` amount of tokens from `from` to `to` using the
     * allowance mechanism. `value` is then deducted from the caller's
     * allowance. Accepts the value as inEuint128, more convenient for calls
     * from other contracts.
     *
     * Returns a boolean value indicating whether the operation succeeded.
     *
     * Emits a {TransferEncrypted} event.
     */
    function _transferFromEncrypted(address from, address to, euint128 value) external returns (euint128);
}
```

### Events

- TransferEncrypted: Emitted when tokens are transferred between accounts.
- ApprovalEncrypted: Emitted when an account grants approval for another account to spend tokens on its behalf.

### Core Functions

- `balanceOfEncrypted(address account, Permission memory auth) external view returns (string memory);`

Returns the encrypted balance of the specified account.

- `transferEncrypted(address to, inEuint128 calldata value) external returns (euint128);`

Transfers the specified encrypted token value to the given address. Suitable for external accounts.

- `_transferEncrypted(address to, euint128 value) external returns (euint128);`

Transfers the specified encrypted token value to the given address. Suitable for contract calls.

- `allowanceEncrypted(address owner, address spender, Permission memory permission) external view returns (string memory);`

Returns the remaining number of tokens that the spender is allowed to spend on behalf of the owner, encrypted.

- `approveEncrypted(address spender, inEuint128 calldata value) external returns (bool);`

Sets the specified encrypted token value as the allowance of the spender over the caller's tokens.

- `transferFromEncrypted(address from, address to, inEuint128 calldata value) external returns (euint128);`

Transfers the specified encrypted token value from one account to another using the allowance mechanism. Suitable for external accounts.

- `_transferFromEncrypted(address from, address to, euint128 value) external returns (euint128);`

Transfers the specified encrypted token value from one account to another using the allowance mechanism. Suitable for contract calls.

## Rationale

The design choices aim to ensure that token transactions remain secure and private. By encrypting the balance, transfer, and allowance values, we can prevent unauthorized access and scrutiny.

## Backwards Compatibility

This proposal introduces a new encrypted token standard and does not directly interfere with the existing ERC20 standard. However, compatibility with ERC20 tokens is not explicitly provided, meaning token holders will need to convert their tokens to utilize the encrypted functionalities.

## Implementation

A reference implementation for this encrypted token standard can be found in the provided Solidity interface and accompanying documentation.

## Security Considerations

Implementing encryption at any level introduces new vulnerabilities, such as key management issues and potential encryption/decryption flaws. It is thus critical to rigorously test any implementation to ensure robustness against these vectors.

## Copyright

All copyrights and related rights are waived under CC0 1.0 Universal.
