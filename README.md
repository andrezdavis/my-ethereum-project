# Ethereum Smart Contract Boilerplate

This project comes with a sample contract, a test for that contract, and a Hardhat Ignition module that deploys that contract.
It uses Alchemy to deploy over Ethereum Sopelia and Goerli networks. It is recommended and is the default case to use the Hardhat network to deploy a smart contract.

## Preparing coin
The contract name has no bearance on name of the coin. To give a coin a name and symbol, edit the ERC20 entry of the constructor signature.
```
contract MyToken is ERC20 {
    constructor(uint256 initialSupply) ERC20("DreToken", "DRE") {
        _mint(msg.sender, initialSupply * (10 ** decimals()));
    }
}
```
Set the <code>PRIVATE_KEY</code> to the wallet private key, you don't have to specify an <code>API KEY</code>.
Store this in the <code>.env</code> in the project root.

## Deploying
First compile the hardhat project.
```
npx hardhat compile
```
Make sure to have at least .001 ETH to cover gas fees.
Deploy the contract.
```
npx hardhat run scripts/deploy.js
```
Check etherscan.io and check your wallet address to see if coins were deployed.

----

The rest of the information regards HardHat specific shell commands:
Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat ignition deploy ./ignition/modules/Lock.js
```
