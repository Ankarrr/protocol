# DMM Protocol

This repository contains the the Ethereum smart contracts for the DeFi Money Market Ecosystem.

### Installation

Firstly, clone the repository to your local machine by running 
`git clone https://github.com/defi-money-market-ecosystem/protocol.git`.

To install the repository's dependencies, run `npm install` (be sure to have already `cd`'ed into the cloned 
repository, first).

### Testing

Tests for the repository are generally broken up into categories and sub-categories for larger suites. To run all tests
at once, run `npm run test`. Doing so uses Open Zeppelin's testing SDK and libraries to spin up a private Ethereum 
chain using [Ganache](https://github.com/trufflesuite/ganache-cli) and runs simple setup for each test in the 
corresponding file's `beforeEach` hook.

To run more specific tests, you can see the ones that are preconfigured in the `package.json` file. Generally, the 
standard is `npm run test-...` where "..." is the category you want to test. To test the controller, run: 
```shell script
npm run test-controller
```
To only test the collateralization functions of the controller, run:
```shell script
npm run test-controller-collateralization
```

### Deployment

Deploying the protocol requires a web3 provider. You can set one via environment variable prior to invoking the script.
For example, to deploy to the Rinkeby Test Network using a pre-configured private key:

```shell script
PROVIDER=https://rinkeby.infura.io/v3/<PROJECT_ID> npm run deploy-testnet
```

This private key is simply `1234567812345678123456781234567812345678123456781234567812345678`.

**DO NOT USE THE PRIOR PRIVATE KEY** for anything other than test network. It is simply a dummy one and anyone would
be able to steal your funds or control your contracts if you use it on the main Ethereum network.

Deploying the protocol to the Ethereum Mainnet requires a private key in addition to a web3 provider. 

You can also deploy the protocol to a local Ethereum Ganache instance running on your machine by getting the port on
which it is running and invoking the following command:

```shell script
PROVIDER=http://localhost:<GANACHE_PORT_NUMBER> npm run deploy-testnet
```

### Docs & Integrating

Read more about the protocol, using it, and integrating it in the [Wiki](https://github.com/defi-money-market-ecosystem/protocol/wiki).
