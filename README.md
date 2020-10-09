# Supply chain & data auditing

This repository containts an Ethereum DApp that demonstrates a Supply Chain flow between a Seller and Buyer. The user story is similar to any commonly used supply chain process. A Seller can add items to the inventory system stored in the blockchain. A Buyer can purchase such items from the inventory system. Additionally a Seller can mark an item as Shipped, and similarly a Buyer can mark an item as Received.

## Important Notes:
* I wasn't able to get Eth from faucets for Rinkeby Test Network from the 2 websites provided in the course, I also wasn't able to find other faucets, so as a result, I deployed my token's contract on the **Ropsten Test Network** instead.
* I used my own Metamask seed when I deployed the token's contract, however, I removed it before putting my code on GitHub, since as we were taught throughout the course, the seed must be kept secret, I also removed my infura key, so in case you want to deploy my code on the Ropsten Test Network to check that it works properly, make sure to put your Metamask seed and infura key (**truffle-config.js** file).
* In case you also want to deploy my contract on the Ropsten Test Network, you might need to change the **gas limit** in the **truffle-config.js** file, as it keeps changing (go to Etherscan, check the gas limit of the last block added in the Ropsten Test Network, and put a value that is smaller than the value shown in a bit).

## Project Requirements:

* Contract Address:0xac8dDa229bf3F4E64dC775eE545a2C065d83d35E

* Transaction Hash: 0x69c112aa3fc2ae028d4f971d00d3a6de048166f280f40c1ee20c56c181562c37

* Node version:v12.18.3

* Truffle version:v5.1.45 (core: 5.1.45)

* Web3 version:v1.2.1 

* UML Diagrams (can also be found inside the UML folder):

	1. Activity Diagram:
	![ActivityDiagram(png)](https://user-images.githubusercontent.com/72036379/95591426-f25ff080-0a4f-11eb-9651-62ba368a58f0.png)
	2. Sequence Diagram:
	![SequenceDiagram(png)](https://user-images.githubusercontent.com/72036379/95589798-ed9a3d00-0a4d-11eb-9b98-2e65c93688e9.png)
	3. State Diagram:
	![StateDiagram(png)](https://user-images.githubusercontent.com/72036379/95589835-fd198600-0a4d-11eb-931d-74ff1de4d969.png)
	4. Class Diagram(Data Model):
	![ClassDiagram(png)](https://user-images.githubusercontent.com/72036379/95589897-0e629280-0a4e-11eb-8763-4a239d8a4e70.png)
  
## Steps Followed After Downloading the Starter Code:

1. I Wrote the missing stuff(functions, modifiers, imports, ...) required in the contracts.
2. In order to deploy it on the local network I used:
  1. ganache-cli (1_start_ganache_cli)
  2. 2_start_node
  3. truffle compile
  4. truffle migrate --> to deploy the contracts on the local network.
  5. truffle test --> to make sure that the tests and my functions are correct, and the 10 tests passed.
  6. npm run dev --> to run the server and be able to test my Dapp (localhost:3000).
  7. Before trying the different functions on the Dapp, I made sure to import addresses and connect to the local network with port 8545.
  8. I tried the different functions and made sure that everything is working properly, I got the transaction history and everything worked fine.
3. In order to deploy it on Ropsten Test Network:
  1. I changed the truffle-config.js file by uncommenting the mnemonic to add my Metamask seed and adding my Infura key, I also uncommented ropsten.
  2. npm install @truffle/hdwallet-provider
  3. I made sure that Metamask is connected to the Ropsten Test Network.
  4. truffle migrate --reset --network ropsten --> it started with 1_initial_migration.js and deployed the Migrations.sol contract, then 2_deploy_contracts.js and deployed FarmerRole.sol, DistributorRole.sol, RetailerRole.sol, ConsumerRole.sol and **SupplyChain.sol** contracts.
  5. npm run dev --> (Dapp was on localhost:3000)
  6. I performed the different functions and was successful as can be seen in the screen shots below:
  
  
  

## Steps that were provided by Udacity:

The DApp User Interface when running should look like...

![truffle test](images/ftc_product_overview.png)

![truffle test](images/ftc_farm_details.png)

![truffle test](images/ftc_product_details.png)

![truffle test](images/ftc_transaction_history.png)


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

Please make sure you've already installed ganache-cli, Truffle and enabled MetaMask extension in your browser.

```
Give examples (to be clarified)
```

### Installing

A step by step series of examples that tell you have to get a development env running

Clone this repository:

```
git clone https://github.com/udacity/nd1309/tree/master/course-5/project-6
```

Change directory to ```project-6``` folder and install all requisite npm packages (as listed in ```package.json```):

```
cd project-6
npm install
```

Launch Ganache:

```
ganache-cli -m "spirit supply whale amount human item harsh scare congress discover talent hamster"
```

Your terminal should look something like this:

![truffle test](images/ganache-cli.png)

In a separate terminal window, Compile smart contracts:

```
truffle compile
```

Your terminal should look something like this:

![truffle test](images/truffle_compile.png)

This will create the smart contract artifacts in folder ```build\contracts```.

Migrate smart contracts to the locally running blockchain, ganache-cli:

```
truffle migrate
```

Your terminal should look something like this:

![truffle test](images/truffle_migrate.png)

Test smart contracts:

```
truffle test
```

All 10 tests should pass.

![truffle test](images/truffle_test.png)

In a separate terminal window, launch the DApp:

```
npm run dev
```

## Built With

* [Ethereum](https://www.ethereum.org/) - Ethereum is a decentralized platform that runs smart contracts
* [IPFS](https://ipfs.io/) - IPFS is the Distributed Web | A peer-to-peer hypermedia protocol
to make the web faster, safer, and more open.
* [Truffle Framework](http://truffleframework.com/) - Truffle is the most popular development framework for Ethereum with a mission to make your life a whole lot easier.


## Authors

See also the list of [contributors](https://github.com/your/project/contributors.md) who participated in this project.

## Acknowledgments

* Solidity
* Ganache-cli
* Truffle
* IPFS
