# AI NFT Generator

## Technology Stack & Tools

- Solidity (Writing Smart Contracts & Tests)
- Javascript (React & Testing)
- [Hardhat](https://hardhat.org/) (Development Framework)
- [Ethers.js](https://docs.ethers.io/v5/) (Blockchain Interaction)
- [React.js](https://reactjs.org/) (Frontend Framework)
- [NFT.Storage](https://nft.storage/) (Connection to IPFS)
- [Hugging Face](https://huggingface.co/) (AI Models)

## Requirements For Initial Setup
- Install [NodeJS](https://nodejs.org/en/)

## Setting Up
### 1. Clone/Download the Repository
```
git clone https://github.com/zalam003/ai_nft_generator.git
```
### 2. Install Dependencies:
```
cd ai_nft_generator
npm install
```

### 3. Setup .env file:
Before running any scripts, you'll want to create a .env file with the following values (see .env.example):

- **ACCOUNT_PRIVATE_KEY=""**
- **REACT_APP_HUGGING_FACE_API_KEY=""**
- **REACT_APP_NFT_STORAGE_API_KEY=**

Create an account on [Hugging Face](https://huggingface.co/). Visit your profile settings, and create a `read` access token. 

Create an account on [NFT.Storage](https://nft.storage/), and create a new API key.

### 4. Name your collection

Edit lines 4, 5 and 6 of `scripts/deploy.js`:

```
  const NAME = "AI Generated NFT"
  const SYMBOL = "AINFT"
  const COST = ethers.utils.parseUnits("1", "ether") // 1 NRG
```

- *NAME* - Name of collection
- *SYMBOL* - Token Symbol
- *COST* - Minting cost


### 5. Update Constructor Arguments

Edit `scripts/constructor-arg.js`. 

```
module.exports = [
    "AI Generated NFT", 
    "AINFT", 
    "1"
];
```

The entires should match the information set in `scripts/deploy.js` in section 4 above.


### 6. Run deployment script

Deploy the smart contract.

```
npx hardhat run ./scripts/deploy.js --network energiTestnet --constructor-args ./scripts/constructor-arg.js
```

### 7. Start frontend

```
npm run start
```

The above will start a web browser instance. If you are using `Brave Browser`, turn shield off to "http://localhost:3000".


### 8. Create and Mint your NFTs

Give a `name` for the image and add a `description` to your NFT. The AI NFT Generator will take the description and create an NFT. Once the NFT is created, it will be posted to IPFS and minted. You will have to pay the minting cost. Once minted, go to [GMI Testnet](https://nrg.test.gonnamakeit.com) to view your collection.

Have fun with your NFTs!

## YouTube Video

This is the video on [Code an A.I. NFT Minting App With Stable Diffusion Step-by-Step](https://www.youtube.com/watch?v=myascjqPnFc).
