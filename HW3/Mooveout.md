1. What are the advantages and disadvantages of the 256 bit word length in the EVM

<aside>
💡 Advantages:

1. **Security**: 256-bit keys provide a very high level of security. It is the standard for most cryptographic algorithms like the ones used in Ethereum for hashing (KECCAK-256) and public-private key pairs (secp256k1). This is crucial for a blockchain where immutability and security are fundamental.
2. **Large Integers**: EVM's large word size allows for the representation and manipulation of very large integers natively. This is very useful for financial calculations that may involve very large numbers, such as those involving tokens with a large supply or tiny fractions of a token.
3. **Optimization**: Ethereum uses the Merkle Patricia tree data structure to store its state. The leaves of this tree are hashed using the KECCAK-256 function, producing a 256-bit hash. Using 256-bit words allows these hashes to be stored, manipulated, and compared efficiently within the EVM.

Disadvantages:

1. **Inefficiency with Small Integers**: Most typical computations do not need numbers anywhere near as large as 2^256. Therefore, a lot of the space in a word is wasted most of the time. This can lead to increased memory usage and decreased efficiency.
2. **Complexity for Developers**: Handling 256-bit numbers can be challenging for developers, especially when dealing with bitwise operations or underflow/overflow vulnerabilities.
3. **Increased Gas Costs**: Operations in EVM are priced in "gas". Larger word size might imply increased gas costs for certain operations.
</aside>

4. What would happen if the implementation of a precompiled contract varied between Ethereum clients?
   Lack of consensus → Hard fork as divergent clients create two different chains
5. Using Remix write a simple contract that uses a memory variable, then using the debugger step through the function and inspect the memory

```jsx
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
