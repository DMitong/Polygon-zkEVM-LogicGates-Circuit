# Polygon zkEVM Circuit Implementation

## Overview 
This project demonstrates how to:
1. Write a correct zk circuit using circom
2. Compile the circuit to generate circuit intermediaries
3. Generate a proof using inputs A=0 and B=1
4. Deploy a Solidity verifier contract on the Polygon zkEVM Cardona Testnet
5. Call the `verifyProof()` method on the verifier contract and assert the output is true.

## Installation 

1. Clone the repository.
2. Navigate to the project's root directory.
3. Install the project dependencies using npm:

```bash
npm install
```

4. Create a `.env` file in the project's root directory and set your private key that has testnet faucets tokens in it:

```env
PRIVATE_KEY='YOUR_SECRET_KEY'
```

## Contract Deployment and Circuit Compilation

To compile the circuit and deploy the verifier contract on the Polygon zkEVM Cardona Testnet, follow these steps:

1. Compile the circuit and generate the `CustomCircuitVerifier.sol` contract:

```bash
npx hardhat circom
```

2. Deploy the contract to the Mumbai Testnet and perform the proof verification:

```bash
npx hardhat run scripts/deploy.ts --network cardona
```

This script will deploy the `CustomCircuitVerifier.sol` contract on the Polygon zkEVM Cardona test network, generate a proof from the circuit intermediaries using `generateProof()`, generate calldata with `generateCallData()`, and finally, call `verifyProof()` on the verifier contract with the calldata deployed to Mumbai.

3. My contract address the verifier contract was deployed to ```0x7425C3E6d636A28840De7bEcec2a136e2DEd88Ca```

## Author

**[Mitong](https://github.com/DMitong)**