# Deploying Your First Smart Contract on Metis Andromeda/Sepolia Network

Welcome to the tutorial for deploying your first smart contract on the **Metis Andromeda/Sepolia** network. This guide will walk you through the entire process, from setting up your environment to deploying a Solidity contract using **Remix**. The steps are designed for new developers and are easy to follow.

---

## Prerequisites

Before you begin, make sure you have the following:

1. **MetaMask Wallet**:
   - Installed and configured on your browser.
   - Added the Metis Andromeda/Sepolia mainnet or testnet.

2. **Test ETH** (if testing on the Metis testnet):
   - Obtain test ETH from the [Metis Faucet](https://faucet.metis.io/).

3. **Basic Knowledge**:
   - Familiarity with Solidity and Ethereum is helpful but not required.

4. **Tools Required**:
   - **Remix IDE**: Browser-based IDE for writing and deploying smart contracts.

---

## Quick Start Guide

### 1. Setting Up Your Environment

1. **Access Remix**:
   - Open [Remix IDE](https://remix.ethereum.org/) in your browser.

2. **Connect MetaMask**:
   - Ensure MetaMask is connected to the Metis Andromeda network.

3. **Create a New File**:
   - Click the **File Explorer** in Remix.
   - Create a new file named `vote.sol`.

   ![Create New File](images/create-new-file.png)

---

### 2. Writing Your First Smart Contract

Copy and paste the following Solidity code into `Vote.sol`:
   - Open the `vote.sol` file in this repository.
   - Copy the code and paste it into the `vote.sol` file in Remix.

---

### 3. Compiling the Contract

1. Navigate to the **Solidity Compiler** tab in Remix.
2. Select `0.8.x` as the compiler version.
3. Click **Compile vote.sol**.
4. Once compiled, a green checkmark will appear.

   ![Compile Contract](images/compile-contract.png)

---

### 4. Deploying the Contract

1. Go to the **Deploy & Run Transactions** tab in Remix.
2. Select **Injected Web3** as the environment (this connects Remix to MetaMask).
3. Input an array of candidate names (e.g., `["Alice", "Bob", "Charlie"]`) in the constructor arguments field.
4. Click **Deploy** and confirm the transaction in MetaMask.
5. Once deployed, the contract will appear in the **Deployed Contracts** section.

   ![Deploy Contract](images/deploy-contract.png)

---

### 5. Interacting with the Contract

- Use the available functions to interact with the deployed contract:
  - **View Candidates**: Call the `getCandidates` function.
  - **Vote for a Candidate**: Use the `vote` function with the candidate's index.
  - **Check Vote Count**: Call the `getVoteCount` function with the candidate's index.

---

## Notes

- **Candidate Indices**: Candidates are indexed starting at `0`.
- **Duplicate Voting**: The contract prevents the same address from voting multiple times.

---

## Troubleshooting

1. **MetaMask Connection Issues**:
   - Ensure you are connected to the correct network in MetaMask.

2. **Deployment Fails**:
   - Check that you have sufficient ETH in your wallet for gas fees.
   - Verify the input parameters for the contract.

---

## Resources

- [Metis Documentation](https://docs.metis.io/)
- [Remix IDE](https://remix.ethereum.org/)

---

## License

This repository is licensed under the MIT License.