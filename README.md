# Monad NFT Minter

A modular, command-line tool for minting NFTs on the Monad blockchain. Simplifies the process of interacting with NFT contracts by automatically detecting the correct mint function and parameters.

## Features

- **Modular Architecture**: Clean separation of concerns for easy maintenance and extensions
- **Multiple Minting Modes**: Choose between Instant or Scheduled minting
- **Smart Contract Integration**: Automatic detection of the correct mint function and parameters
- **Auto Price Detection**: Automatically retrieves mint price from contracts
- **Scheduled Minting**: Automatically start minting at the contract's specified launch time
- **Simple Wallet Management**: Easy configuration through environment variables
- **Collection Details**: Displays collection name and supply information when available
- **Magic Eden Link Support**: Paste a Magic Eden mint link directly to extract the contract address

## Installation

1. Clone the repository:

```bash
git clone https://github.com/holmesairs/ME-MINT.git
cd ME-MINT
```

2. Install dependencies:

```bash
npm install inquirer chalk ethers
```

3. Configure your wallet:

   Add your private key to the `.env` file:

   ```
   NETWORK=monad-testnet
   MAX_CONCURRENT_MINTS=10
   DEFAULT_GAS_LIMIT_MIN=180000
   DEFAULT_GAS_LIMIT_MAX=280000
   PRIVATEKEY=0xYourPrivateKeyHere
   ```

   ⚠️ **IMPORTANT**: Never share your `.env` file or expose your private keys.

## Usage

Start the minting tool:
```
#Start
npm start
```

Follow the interactive prompts to:

1. Choose between Instant Mint or Scheduled Mint
2. Enter the NFT contract address or a Magic Eden link
   - You can paste a link like `https://magiceden.io/mint-terminal/monad-testnet/0x0000000000000`
   - Or enter the contract address directly
3. Choose to retrieve the mint price from the contract or enter manually

### Example


? Minting Mode: Instant Mint
? NFT Contract Address or Magic Eden Link: https://magiceden.io/mint-terminal/monad-testnet/0x000000000000000
> Using contract address: 0x00000000000000
> Collection: MyNFTCollection (MNFT)
? Get price from contract? Yes
+ Price obtained from contract - [0.0001 MON]
> Supply: 999999
> Using gasLimit: [267348] globalMintVariant: [fourParams]
> Wallet is minting 1 NFT(s)
+ Mint transaction sent! [0x0000...000]
  https://testnet.monadexplorer.com/tx/000000000
+ Transaction confirmed in Block [6290517]
+ Minting process completed!
