# Homework 4

##### 1. Why cannot Bitcoin use the consensus protocol Google or Facebook uses to update their distributed databases?

Bitcoin goal is to make an object (coin) that others cannot transfer freely. if Bitcoin store in centralized platform, platform owner will has access to your coin (definitely no good). So Google or Facebook, which is a centralized platform, is not appropriate for Bitcoin.

##### 2. Why would we ever want a distributed database with decentralized control?

Distributed database will not be controlled by authority (cloud host, big company--AWS, Oracle, Google, etc).

##### 3. What really is a Bitcoin?

Bitcoin is the world's first and largest cryptocurrency, created by Satoshi Nakamoto (pseudonym) in 2009.

##### 4. What really is a blockchain?

Blockchain is a transaction protocol. Its objective is to validation an object (aka contact) using other parties (miners).

##### 5. How can you prove to the world that you are the owner of a Bitcoin account?

To prove your authority, you need to show your digital signature.

##### 6. Why is proof-of-work necessary in Bitcoin consensus?

The proof-of-work is a proof to determine who will get the contacted Bitcoin after solve the task equitation.

##### 7. What happens when valid blocks are discovered at about the same time and forking occurs?

After the forking, they will wait a litter while, and then check which fork have more people. The one with the more people will be valid, the another will be invalid.

##### 8. What is the role of a Bitcoin miner and why would anyone want to become one?

Bitcoin miners are people who rental their processors to blockchain network, to receive promise fee (in this case, it is some Bitcoin from the gas fee) of proof-of-work. Most Bitcoin miners doing this because they believe that the promise fee they receive have more value than the costs they invest (GPUs cost, internet cost, electricity cost, etc.).

##### 9. How does Bitcoin deal with malicious nodes that are out there to destroy it?

In that case, other nodes (good nodes) will revert what malicious nodes have done.

##### 10. When people say that Bitcoin is secured, what do they actually mean?

- In terms of legal: Bitcoin is secure as valuable money since it was accepted by the law in the U.S., Japan, the U.K., and most other developed countries.
- In terms of economy: It said to be secure, since some accredited investors giving their trust in Bitcoin, so it has potential.
- In terms of technology: It is more secure than other coins that deploy on centralized applications. Since Bitcoin does not depend on any host, no host can access your account storage.

##### 11. In a nutshell, what exactly is Ethereum?

Ethereum is a decentralized, open-source blockchain. (It is a network)

##### 12. In a nutshell, what exactly is a smart contract?

Smart contract is a code template for creating objects in an open transaction protocol (Blockchain network). The objects can't be edit/update/modify after deploy to the network.

##### 13. “Ethereum with only EOA and without contract accounts is the same as Bitcoin.” Do you agree or disagree with this statement and why?

Agree! Ethereum and Bitcoin have only one different that is the contact account (EOA - Externally Owned Account). So without account Ethereum is no different from a cryptocurrency.

##### 14. Why would anyone want to use Solidity instead of EVM assembly (bytecode) for developing smart contracts?

VM assembly is a low level programming language, it not easy to do the object-oriented programming (harder for developing).

##### 15. Why are gas and fee necessary in Ethereum?

The creators of Ethereum wanted to make sure someone couldn't clog up the network with an infinite loop, or hog all the network resources with really intensive computations. So they made it so transactions aren't free, and users have to pay for computation time as well as storage.

##### 16. When will there be state change in the Ethereum network?

The state changed when the transaction occurs between block to block according to a pre-defined set of rules (defined by EVM).

##### 17. Why cannot RISC-V or Intel X86 memory model be applied to that of Ethereum?

The Ethereum virtual machine model offers 256-bit address space. But RISC-V / Intel X86 can only provide 64-bit at maximum, so their address space is not enough to apply with Ethereum.

##### 18. What does revert() do when executed?

The revert() will undo all state changes. But it allows you to return a value and refunds any remaining gas to the caller.

##### 19. What do msg.sender and msg.value represent?

`msg.sender` - The special global variable to obtain the `current user’s address` from where the function call came from

`msg.value` - The `amount of wei` sent with a message to a contract (wei is a denomination of ETH)

##### 20. Identify at least two problems with the following smart contract

```sol
contract MyRegistry {

    mapping (string => address) public registry;

    function registerDomain(string memory domain) public {
        // Can only reserve new unregistered domain names
        require(registry[domain] == address(0));

        // Update the owner of this domain
        registry[domain] = msg.sender;
    }
}
```

1. Missing solidity version
2. Dynamically-sized keys for public mappings are not supported. -> change public 'registry' to internal (or private)
3. (Maybe) Missing domain validation, for example:
   - Is domain open for registration?
   - Is domain really exist?
   - Is current user really domain owner?
4. It will be better to make another internal function to run `registry[domain] = msg.sender`, instead of run it directly in public function
