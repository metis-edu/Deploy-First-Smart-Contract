# Deploying Your First Smart Contract on Metis Andromeda/Sepolia Network

Welcome to the tutorial for deploying your first smart contract on the **Metis Andromeda/Sepolia** network. This guide will walk you through the entire process, from setting up your environment to deploying a Solidity contract using **Remix**. The steps are designed for new developers and are easy to follow.

---

## Prerequisites

Before you begin, make sure you have the following:

1. **MetaMask Wallet**:
   - Installed and configured on your browser.
   - Added the Metis Andromeda/Sepolia mainnet or testnet.
   ![<MetaMask Connection>](https://private-user-images.githubusercontent.com/80626423/398081117-73f73208-d65f-4753-b16e-ab7453073dc8.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMTctNzNmNzMyMDgtZDY1Zi00NzUzLWIxNmUtYWI3NDUzMDczZGM4LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAzYzYyZDM2ODUwOTk1NjA2NWFkMTJkMDE1YTgwOGUxNGRmNDRiMzFmYmFhYjgxMmUwNjE3ZTg0MTY5NDcxMzQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.CDd5osKkBs6NLTMWqjm1gU28IM4SLHXo-W-DxENAqZs)

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
   - Ensure MetaMask is connected to the Metis Andromeda/Sepolia network.
   ![Metamask is connected](https://private-user-images.githubusercontent.com/80626423/398081119-727b9104-cf71-4b86-a9f5-92079435f1c0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMTktNzI3YjkxMDQtY2Y3MS00Yjg2LWE5ZjUtOTIwNzk0MzVmMWMwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWRjYzQ2NmE0MTE0ZWE1NjBkZmQxNDI3NTUzNWIxNDg0NzQ2OTBmYWMzMThmODI5NWFjM2EyZjJlNGY2Y2I0ZDkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.oHkdH-8IZkgkOVLOwrfDQQQ_QD7KuDOU04l7BCf6B7Q)

3. **Create a New File**:
   - Click the **File Explorer** in Remix.
   - Create a new file named `vote.sol`.

   ![Create New File](https://private-user-images.githubusercontent.com/80626423/398081121-7b7ad470-9b77-4efa-916e-bdfca4dd2913.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMjEtN2I3YWQ0NzAtOWI3Ny00ZWZhLTkxNmUtYmRmY2E0ZGQyOTEzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTQ0ODYzNGUzNmY1NDUzOTc4YmIyNWJlZTY2ODk5ZGJkMzRmZDEyMTU2OGI2NmNkNzEzNmQ5ZjJlZTMxOTZjYzUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.236Mdh5gdijd_mfQKWe7HwbXV208N9lIzBb6GPmVz8c)

---

### 2. Writing Your First Smart Contract

Copy and paste the following Solidity code into `Vote.sol`:
   - Open the `vote.sol` file in this repository.
   - Copy the code and paste it into the `vote.sol` file in Remix.
![Write contract](https://private-user-images.githubusercontent.com/80626423/398081124-2973bbb1-397c-4c58-b4ec-99253a8e1d23.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMjQtMjk3M2JiYjEtMzk3Yy00YzU4LWI0ZWMtOTkyNTNhOGUxZDIzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTM1ZWQ3YmFlMGY5YzY4ZTA2OWNlOWVlYTA2NjVkOWEwZDM5ZDk4MzdiZmE1NjQ2MjAwNTIyOTM2MjJmNTJiOWEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.Tt1V9PXd2iNpIci0f1_QLCOUPVwxF4jPSfVsZuyFULs)
---

### 3. Compiling the Contract

1. Navigate to the **Solidity Compiler** tab in Remix.
2. Select `0.8.x` as the compiler version.
3. Click **Compile vote.sol**.
4. Once compiled, a green checkmark will appear.

   ![Compile Contract](https://private-user-images.githubusercontent.com/80626423/398081127-9d4b7485-e152-406e-b4df-838fb607a6b0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMjctOWQ0Yjc0ODUtZTE1Mi00MDZlLWI0ZGYtODM4ZmI2MDdhNmIwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWE5NmM4NDMwYWJjNGE2NWI1ZGZiNzMwMTkxZGJkMjgwOTgyNzA2ZGI4OWQ2Y2M0YmJkNGVjOWUwYzVkNTE1ODImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.jik9bX7BzXhqEmEgXQ6xh-fVZ1BWhjniWApZFJel8pM)

---

### 4. Deploying the Contract

1. Go to the **Deploy & Run Transactions** tab in Remix.
2. Select **Injected Web3** as the environment (this connects Remix to MetaMask).
3. Input an array of candidate names (e.g., `["Alice", "Bob", "Charlie"]`) in the constructor arguments field.
4. Click **Deploy** and confirm the transaction in MetaMask.
5. Once deployed, the contract will appear in the **Deployed Contracts** section.

   ![Deploy Contract](https://private-user-images.githubusercontent.com/80626423/398081129-a0f54638-ca98-4f4d-9a4c-9acb6aa12460.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMjktYTBmNTQ2MzgtY2E5OC00ZjRkLTlhNGMtOWFjYjZhYTEyNDYwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTNlZWU2MzExYWYzM2VhZmIzNzVlYmE2YjJjYzg1YTE5NWY5NDdiNTE2NjRjZGJiNmUxYzAxZWEyNzNjMDk3MzAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.jkqc0isULAbcJmoq045AIAeFhjprOwrvxx_ymD8JmoE)
   ![Interact Contract](https://private-user-images.githubusercontent.com/80626423/398081132-a62ed285-c9f4-48ad-aff1-e0430a494781.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMzItYTYyZWQyODUtYzlmNC00OGFkLWFmZjEtZTA0MzBhNDk0NzgxLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAzYzc3YzhhMDNjMzI3YWJlYTk4MzM5NjQxNzE5ZWZkMDlmZjUzNTNiM2Q3MDhhYzIzNDAxZWIyYjlmZmU0MmQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.N6gTC7RaRwov-Cq8zm7tyBHj-0ClgxPl-Hs6NCe5DLI)

---

### 5. Interacting with the Contract

- Use the available functions to interact with the deployed contract:
  - **View Candidates**: Call the `getCandidates` function.
  - **Vote for a Candidate**: Use the `vote` function with the candidate's index.
  - **Check Vote Count**: Call the `getVoteCount` function with the candidate's index.
   ![Interact Contract](https://private-user-images.githubusercontent.com/80626423/398081130-c9ead46d-1eed-4a5d-9465-cb31f46fb454.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzQ5MzgyODUsIm5iZiI6MTczNDkzNzk4NSwicGF0aCI6Ii84MDYyNjQyMy8zOTgwODExMzAtYzllYWQ0NmQtMWVlZC00YTVkLTk0NjUtY2IzMWY0NmZiNDU0LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEyMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMjIzVDA3MTMwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWQ3NDVkYzZjYTU2ZjNkMGU0ZmU0YTQ4NDA4ZjIzOTU0ODc3MTRlZDJlM2YxY2M1MDhkZWFlZWE0MTFjZmJhYjkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.TxVlRbQG7BUsCFEAy4mZBLl7L4noQ3NJZ91uJkcMltY)

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