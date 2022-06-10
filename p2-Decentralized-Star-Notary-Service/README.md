# ND1309 C2 Ethereum Smart Contracts, Tokens and Dapps - Project Starter 
**PROJECT: Decentralized Star Notary Service Project** - For this project, you will create a DApp by adding functionality with your smart contract and deploy it on the public testnet.

**ERC-721 Token Name** -  StarNotary Token

**ERC-721 Token Symbol** - SNT

**“Token Address” on the Ropsten Network** - 0x88746437cC7e2e77dBa92Fd646E2954884ee4B55

### Dependencies
For this project, you will need to have:
1. **Node and NPM** installed - NPM is distributed with [Node.js](https://www.npmjs.com/get-npm)
```bash
# Check Node version
node -v
# Check NPM version
npm -v
```


2. **Truffle v5.4.22** - A development framework for Ethereum. 
```bash
# Install
npm install -g truffle
# Specify a particular version
npm install -g truffle@5.4.22
# Verify the version
truffle version
```


2. **Metamask** - If you need to update Metamask just delete your Metamask extension and install it again.


3. [Ganache](https://www.trufflesuite.com/ganache) - Make sure that your Ganache and Truffle configuration file have the same port.


4. **Other mandatory packages**:
```bash
# install packages
npm install @openzeppelin/contracts
npm install @truffle/hdwallet-provider
npm install webpack-dev-server -g
npm install web3
```

***packages version:*** Ensure using right version:

| Package | Version |
|---|---|
| @openzeppelin/contracts | ^4.6.0 |
| @truffle/hdwallet-provider | ^2.0.8 |

**Compilers solc version:** Ensure the following in `truffle-config.js`:
```js
// ...
const HDWalletProvider = require("@truffle/hdwallet-provider");
const infuraKey = "<Your Infura ProjectId>";
const mnemonic = "<Your Metamask Secret Recovery Phrase>";

// ....


ropsten: {
  provider: () => new HDWalletProvider(mnemonic, `https://ropsten.infura.io/v3/${infuraKey}`),
  network_id: 3,       // Ropsten's id
  // ....
},

// ...

// Configure your compilers  
compilers: {    
  solc: {      
    version: "0.8.13", // <- Use this        
    // docker: true,
    // ...
```

### Run the application
1. Clean the frontend 
```bash
cd app
# Remove the node_modules  
# remove packages
rm -rf node_modules
# clean cache
npm cache clean
rm package-lock.json
# initialize npm (you can accept defaults)
npm init
# install all modules listed as dependencies in package.json
npm install
```

2. Start Truffle by running
```bash
# For starting the development console
truffle develop
# truffle console

# For compiling the contract, inside the development console, run:
compile

# For migrating the contract to the locally running Ethereum network, inside the development console
migrate --reset

# For running unit tests the contract, inside the development console, run:
test
```

3. Frontend - Once you are ready to start your frontend, run the following from the app folder:
```bash
cd app
npm run dev
```

---

### Important
When you will add a new Ropsten Test Network in your Metamask client, you will have to provide:

| Network Name | New RPC URL | Chain ID |
|---|---|---|
|Ropsten Network|`https://ropsten.infura.io/v3`|3 |

The chain ID above can be fetched by:
```bash
cd app
node index.js
```

## Troubleshoot
#### Error 1 
```
'webpack-dev-server' is not recognized as an internal or external command
```
**Solution:**
- Delete the node_modules folder, the one within the /app folder
- Execute `npm install` command from the /app folder

After a long install, everything will work just fine!