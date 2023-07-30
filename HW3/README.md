# Answers for HW3

**1. What are the advantages and disadvantages of the 256-bit word length in the EVM**\
Advantages:
- Compatibility with Cryptographic Algorithms: Many cryptographic algorithms, such as SHA-256 and ECDSA, are designed to work with 256-bit integers.
Using a 256-bit word length in the EVM allows for direct implementation of these algorithms without the need for conversions or truncation.
- Large Data Capacity: A 256-bit word length allows the EVM to handle very large integers, providing high precision for mathematical calculations and cryptographic operations.
It enables complex operations and supports big numbers that might be encountered in cryptography and financial applications.\

Disadvantages:
- Memory Consumption: A 256-bit word length can lead to higher memory consumption compared to smaller word lengths, especially when dealing with arrays or large data structures. This can result in higher gas costs for memory-intensive operations.
- Storage Costs: Storing large 256-bit data can consume more storage space on the blockchain, potentially leading to higher costs for contract deployment and maintenance.
- Performance Impact: Performing operations on 256-bit numbers can be more computationally expensive than using smaller word sizes. This can impact the execution speed and efficiency of smart contracts, especially in cases where a smaller word length would be sufficient.

**2. What would happen if the implementation of a precompiled contract varied between Ethereum clients?**\
If the implementation of a precompiled contract varies between Ethereum clients, it can lead to consensus issues and potential security vulnerabilities. Consistency is crucial to ensure a unified and secure Ethereum network.

**3. Using Remix write a simple contract that uses a memory variable, then using the debugger step through the function and inspect the memory.**
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract DebuggingPractice {
    
    function manipulateArray() public pure returns(uint256) {
        uint256[] memory numbers = new uint256[](5);
        
        for(uint i = 0; i < numbers.length; i++) {
            numbers[i] = i;
        }
        
        uint256 sum = 0;
        
        for(uint i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        
        return sum;
    }
}
```
