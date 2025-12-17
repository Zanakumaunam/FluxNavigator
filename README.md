# FluxNavigator

Built for Base

FluxNavigator is a compact Base-oriented repository designed to observe network state, wallet connectivity, and JSON-RPC consistency across Base environments using official Coinbase tooling.

The project deliberately avoids complex application logic and instead focuses on infrastructure visibility and repeatable onchain read validation.

## Purpose and Scope

FluxNavigator exists to:
- Verify Base Mainnet and Base Sepolia connectivity
- Exercise OnchainKit wallet connection flows
- Perform deterministic, read-only RPC calls
- Surface clear Basescan references for inspection

## Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

## Runtime Behavior

Primary file: `app/fluxNavigator.ts`

When executed, the application:
- Initializes an OnchainKitProvider bound to the selected Base chain
- Presents wallet connection UI
- Uses Viem to query:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a supplied address
- Displays Basescan explorer URLs for transparency

## Project Structure

app/  
- fluxNavigator.ts  
  React entry point combining OnchainKit wallet components with Base RPC reads.

Expected companion files:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env (optional)

## Libraries

OnchainKit  
Wallet UX components and Base-first primitives  
https://github.com/coinbase/onchainkit  

Viem  
EVM client for Base JSON-RPC reads  

## Installation and Usage

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run with a standard React/Vite or Next.js development server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## License

MIT License

## Author

GitHub: https://github.com/Zanakumaunam 

Public contact (email): sloops.glam.0l@icloud.com

Public contact (X): https://x.com/jennifer_ck7

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0xf81768c6fcfde5f62e7340b1adc6ef1113cd7822

Deployment and verification:
- https://sepolia.basescan.org/address/0xf81768c6fcfde5f62e7340b1adc6ef1113cd7822
- https://sepolia.basescan.org/0xf81768c6fcfde5f62e7340b1adc6ef1113cd7822/0#code  

Contract #2 address:  
0xbbf4ff821bf2c008d0a9c7cd02cf879cb39dbe83 

Deployment and verification:
- https://sepolia.basescan.org/address/0xbbf4ff821bf2c008d0a9c7cd02cf879cb39dbe83
- https://sepolia.basescan.org/0xbbf4ff821bf2c008d0a9c7cd02cf879cb39dbe83/0#code  
