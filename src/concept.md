# Concept

## Background

There are various bridges existing in the market, aiming to establish cross-chain connections among different chains. 

## POA TokenBridge

The [POA TokenBridge](https://docs.tokenbridge.net/) provides a generic bridge between Ethereum based chains. Multiple bridge modes are supported by POA TokenBridge, for different purposes of data transfer, e.g. ERC20 to ERC20, AMB(Arbitrary Message Bridge). With the AMB mode, arbitrary messages can be transferred across chains, which means NFTs can be also transferred between networks via this bridge mode. 

## Proof of Concept

With the implementation of POA TokenBridge, a cross-chain bridge between Ethereum and Polkadot can be easily established. With the benefit of Substrate, we are able to establish a parachain of Polkadot with [EVM Pallet](https://substrate.dev/docs/en/knowledgebase/smart-contracts/evm-pallet). And the POA bridge will perfectly fit the gap between the EVM Pallet equipped parachain of Polkadot and the Ethereum network, and connect these two networks to communicate from each other. 

However, this solution requires offline oracle nodes to relay and forward messages from both direction, and it is still heavily relying on the EVM environment and Solidity contracts on Polkadot side. It is not a native solution for Polkadot. 

In order to make full use of the existing resources, and to maximize the power of Substrate, we plan to implement the whole oracle part with **Off-Chain Workers** inside our Runtime. The benefits of doing this are:

* Security improvement of on-chain implementation comparing to offline oracles
* Better performance with native code implementation
* Easy to access chain states

Moreover, with the flexibility of Runtime implementation, we will add support of dynamic NFT from ChainLink in the future development phase. 