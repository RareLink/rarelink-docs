# FAQ

## Why dynamic NFT is important?
* Most existing NFTs are static and created by ERC721 standard, so they are limited to
Ethereum network and won’t response to real-world events;
* There are a lot of business use cases demand dynamic NFT (e.g., ticketing, sports, etc.),
where NFTs need to dynamically response to real-world events (such as time, market
price, weather data, flight status, etc.) and update themselves in real-time.
* With the help of dynamic NFT, tons of new applications will be enabled and it will
become the next revolution in NFTs and Blockchain domain.
* See more use cases currently from [Chainlink blog](https://blog.chain.link/create-dynamic-nfts-using-chainlink-oracles/).

## Why a new token bridge is needed for dynamic NFT? What is the difference from existing token bridge?

* All existing token bridges (e.g., POA token bridge, Parity token bridge, and ChainSafe/Centrifuge chainbridge) are implemented to transfer static tokens such as ERC20 or ERC721 tokens.
* They are not able to relay the update events for dynamic NFTs, therefore, the dynamic NFTs will lose dynamic behavior after cross-chain transfer. Literally, they become static NFTs afterwards. Therefore, existing bridges are not suitable.
* The unique characteristic of dynamic NFTs require a new token bridge to keep track of their dynamic behavior across different networks.
* ***RareLink*** protocol aims to close the gap and create a new two-way bridge for dynamic NFT to enable more business use cases in both ecosystems.

## What is the challenge to build a new token bridge for dynamic NFT?

* The first challenge is the relay of update events:
  * The update event is triggered in one blockchain and needs to be passed to another blockchain, which can be an arbitrary message used to retain the same dynamic behavior across networks.
  * It is a great challenge to transfer the update even across the bridge with high fidelity and update the dynamic NFT correctly.

* The second challenge is to provide high reliability:
  * The token transfer may fail due to various reasons (e.g., message queue is broken, event message is failed to be received, etc.) and user will lose their tokens in that case. 
  * ***RareLink*** protocol will keep high reliability as the top priority in the design of the new token bridge. Many new techniques (e.g., retrying, validation, etc.) will be created for this purpose.


