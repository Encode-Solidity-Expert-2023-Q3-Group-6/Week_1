1. Why is client diversity important for Ethereum?
   Prevent liveness failure due to single client → See Solana, Infura outage
2. Where is the full Ethereum state held?
   On the Ethereum state machine onchain
3. What is a replay attack?
   Replaying the same transaction on a different chain
   What can prevent it?
   ChainID
   Private message? Adding a signed message
4. In a contract, how do we know who called a view function?
   Not possible
   Possibly have to rely on Etherscan to check which transactions have been made to contract
