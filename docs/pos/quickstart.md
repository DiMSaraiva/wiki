---
id: getting-started
title: Get Started with Polygon PoS
sidebar_label: Quick Start
description: "Build your next blockchain app on Polygon."
keywords:
  - docs
  - matic
  - polygon
  - build on polygon
  - blockchain
  - introduction
  - how to launch dapp
  - dapps
  - ethereum
image: https://wiki.polygon.technology/img/polygon-logo.png
---

This guide will introduce you to the Polygon PoS ecosystem. You'll find links to valuable resources and websites that will bring you up to speed on building, not only on Polygon but also on general blockchain application development.

:::tip Stay in the know

Keep up with the latest builder updates from the Polygon
team and the community by subscribing to the
[<ins>Polygon notification groups</ins>](https://polygon.technology/notifications/).

:::

## Building on Polygon

If you are an Ethereum developer, you are already a Polygon developer. Simply switch to the [Polygon RPC](https://polygon-rpc.com/) and get started. All the tools you are familiar with on the Ethereum blockchain are supported on Polygon by default, such as Truffle, Remix, and Web3js.

You can deploy decentralized applications to either Polygon Mumbai Testnet or the Mainnet. The Polygon Mumbai Testnet connects with the Ethereum Goërli Testnet, which acts as its ParentChain. You can find all the network-related details in the [network documentation](https://github.com/0xPolygon/wiki/blob/master/docs/operate/network.md).

### Wallets

To interact with the Polygon Network, you need to have an Ethereum-based wallet because Polygon runs on Ethereum Virtual Machine (EVM). You can choose to set up a [Metamask](https://github.com/0xPolygon/wiki/blob/master/docs/tools/wallets/metamask/overview.md) or [Arkane](https://github.com/0xPolygon/wiki/blob/master/docs/develop/wallets/arkane/intro_arkane.md) Wallet. More on wallet-related information and why you need one can be found in our [wallet documentation](https://docs.polygon.technology/docs/develop/wallets/getting-started).

### Smart Contracts

Polygon supports many services you can use to test, compile, debug, and deploy decentralized applications onto the Polygon Network. These include deployment using [thirdweb](https://github.com/0xPolygon/wiki/blob/master/docs/develop/thirdweb.md), [Alchemy](https://github.com/0xPolygon/wiki/blob/master/docs/develop/alchemy.md), [Chainstack](https://github.com/0xPolygon/wiki/blob/master/docs/develop/chainstack.md), [QuickNode](https://github.com/0xPolygon/wiki/blob/master/docs/develop/quicknode.md), [Remix](https://github.com/0xPolygon/wiki/blob/master/docs/develop/remix.md), [Truffle](https://github.com/0xPolygon/wiki/blob/master/docs/develop/truffle.md), [Hardhat](https://github.com/0xPolygon/wiki/blob/master/docs/develop/hardhat.md), and [Replit](https://github.com/0xPolygon/wiki/blob/master/docs/develop/replit.md).

### Connecting to Polygon

You can add Polygon to MetaMask or directly use Arkane, which allows you to connect to Polygon using [RPC](https://docs.polygon.technology/docs/tools/wallets/metamask/config-polygon-on-metamask/).

:::note Directory of publicly available PoS RPC endpoints

Check out a list of public endpoints for the Polygon PoS network at [Alchemy's Chain Connect resource](https://www.alchemy.com/chain-connect/chain/polygon-pos) and [Chainlist](https://chainlist.org/chain/137).

:::

In order to connect with the Polygon network to read blockchain information, we recommend using the Alchemy SDK.

```js
// Javascript
// Setup: npm install alchemy-sdk
const { Alchemy, Network } = require("alchemy-sdk");

const settings = {
  apiKey: "demo", // Can replace with your API Key from https://www.alchemy.com
  network: Network.MATIC_MAINNET, // Can replace with MATIC_MUMBAI
};

const alchemy = new Alchemy(settings);

async function main() {
  const latestBlock = await alchemy.core.getBlockNumber();
  console.log("The latest block number is", latestBlock);
}

main();
```

## Get Started with Web3Modal

:::caution Content disclaimer

Please view the third-party content disclaimer [<ins>here</ins>](https://github.com/0xPolygon/wiki/blob/master/CONTENT_DISCLAIMER.md).

:::

### Overview

[<ins>Web3Modal</ins>](https://web3modal.com/) is a simple and intuitive SDK that provides a drop-in UI to enable users of any wallet to seamlessly log in to applications, offering a unified and smooth experience. It features a streamlined wallet selection interface with automatic detection of various wallet types, including mobile, extension, desktop, and web app wallets.

### Code Sandbox for Polygon

The Web3Modal team has prepared a [<ins>Polygon Code Sandbox</ins>](https://codesandbox.io/p/sandbox/web3modal-v3-polygon-7264l5?file=/src/main.tsx:9,19-9,50). It’s a straightforward way for developers to integrate and get hands-on experience with Polygon.

### How to Integrate

1. **Visit Web3Modal:** Go to [<ins>Web3Modal's official website</ins>](https://web3modal.com/) to explore its features and capabilities.
2. **Explore the Code Sandbox:** Utilize the [<ins>Polygon Code Sandbox</ins>](https://codesandbox.io/p/sandbox/web3modal-v3-polygon-7264l5?file=/src/main.tsx:9,19-9,50) to demo and understand the integration process.
3. **Follow the Documentation:** Refer to the provided documentation and instructions to integrate Web3Modal into your projects and leverage its features effectively.

## Building a new dApp on Polygon?

Decentralized applications (dApps) act as the bridge between users and their data privacy on the blockchain. The increasing number of dApps validates their usefulness within the blockchain ecosystem, solving challenges like executing transactions between two participants without the need for central authority via smart contracts.

Suppose you have no prior experience building decentralized applications (dApps). In that case, the below-mentioned resources will give you a head start on the tools required to build, debug, and deploy dApps on the Polygon Network.

- [Full Stack dApp: Tutorial Series](https://kauri.io/full-stack-dapp-tutorial-series/5b8e401ee727370001c942e3/c)
- [Web3.js](https://www.dappuniversity.com/articles/web3-js-intro)
- [Ethers.js](https://docs.ethers.io/v5/)
- [thirdweb](https://portal.thirdweb.com)
- [Remix](https://docs.polygon.technology/docs/develop/remix/)
- [Truffle](https://docs.polygon.technology/docs/develop/truffle)
- [Metamask](https://docs.polygon.technology/docs/tools/wallets/metamask/overview)
- [Arkane](https://docs.polygon.technology/docs/develop/wallets/arkane/intro)
- [Develop a dApp using Fauna, Polygon and React](https://docs.polygon.technology/docs/develop/dapp-fauna-polygon-react)

## Already have a dApp?

If you already have a decentralized application (dApp) and are looking for a platform to help you scale efficiently, then you are at the right place because Polygon allows you to:

1. **Easily migrate from Ethereum Virtual Machine (EVM) based chain**: Polygon prides itself in being the ultimate Layer-2 scaling solution for Ethereum. You don't have to worry about the underlying architecture while moving or deploying your dApps to the Polygon Network as long as it is EVM-compatible.
2. **Use Polygon as a faster transaction layer**: Deploying your dApp to the Polygon Mainnet allows you to leverage Polygon as a faster transaction layer for your dApp. Additionally, you can get your tokens mapped by us. You can join our [technical discussions group](http://bit.ly/matic-technical-group) on Telegram to learn more.

## Side Note

If this is overwhelming, that’s alright! You can jump right into the action and start hacking. Here are some notes before you start diving into resources, repositories, and docs:

1. **Beware the cost of being on the bleeding edge**: Like typical niche programming, dApps and blockchain development moves very quickly. While researching, you may find complex code repositories, 404s on a documentation site, or even no documentation. Use that opportunity to reach out to us via any social media channel.
2. **The learning curve may be daunting, but the barrier to entry is low**: The community is very open and welcoming! Projects welcome pull requests from outsiders and resolve any blockers actively. We’re working on creating a better world and contribution in any form is appreciated. We’ll be grateful to onboard you into this amazing Web3 ecosystem.

:::info Stay Updated

Decentralized application development encourages network decentralization. Follow our social media handles for more insights and updates about the Polygon ecosystem. You can find the links to all the Polygon communities [here](https://polygon.technology/community/).

:::
