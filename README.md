# Bitcoin

## Overview

Bitcoin is a new digital currency that uses peer-to-peer technology to operate with no central authority or banks; managing transactions and the issuing of bitcoins is carried out collectively by the network.

Version: 0.1.0
Release Date: January 9, 2009
Author: Satoshi Nakamoto
License: MIT License

## Introduction

Bitcoin is an experimental digital currency that enables instant payments to anyone, anywhere in the world. Bitcoin uses peer-to-peer technology to operate with no central authority: transaction management and money issuance are carried out collectively by the network. 

The original Bitcoin software by Satoshi Nakamoto was released under the MIT license. Most client software, derived or "from scratch", also use open source licensing.

## Installation

### System Requirements

- Windows XP/Vista
- At least 512MB of RAM
- At least 100MB of disk space

### Building from Source

#### Windows
1. Download and install MinGW and MSYS
2. Clone the repository
3. Navigate to the source directory
4. Run `make -f makefile.mingw`
5. The executable will be created as `bitcoin.exe`

## Running Bitcoin

When you first run Bitcoin, it will create a data directory in:

- Windows: `%APPDATA%\Bitcoin`

The software will automatically download the blockchain when first run. Please be patient as this can take some time depending on your connection speed.

## Features

- Send and receive bitcoins
- Maintain a wallet with your bitcoin balance
- View transaction history
- Mining capability to generate new bitcoins
- Connect to the peer-to-peer network

## Technical Architecture

Bitcoin consists of several key components:

### 1. Blockchain
The blockchain is a public ledger that records all transactions. It's implemented as a chain of blocks, each containing a set of transactions. 

### 2. Transactions
Bitcoin uses a UTXO (Unspent Transaction Output) model. Each transaction references previous transaction outputs as new transaction inputs and creates new outputs that can be spent in future transactions.

### 3. Script
Bitcoin uses a stack-based scripting system for transaction validation and to create various spending conditions.

### 4. Mining
Mining is the process of adding transaction records to the public ledger (blockchain). It's also the mechanism used to introduce new bitcoins into the system.

### 5. Network
Bitcoin operates on a peer-to-peer network where nodes can validate transactions, add them to their copy of the ledger, and then broadcast these ledger additions to other nodes.

### 6. Wallet
The wallet stores the private keys necessary to spend the bitcoins associated with your addresses.

## Key Files

- **main.cpp/h**: Core blockchain logic
- **script.cpp/h**: Transaction script interpretation
- **db.cpp/h**: Database functionality for blockchain and wallet
- **net.cpp/h**: Peer-to-peer networking
- **wallet.cpp/h**: Wallet functionality
- **miner.cpp/h**: Mining implementation
- **ui.cpp/h**: User interface code

## Configuration

Bitcoin can be configured through the `bitcoin.conf` file located in the data directory. Example settings:

```
# Network-related settings
maxconnections=16
proxy=127.0.0.1:9050

# JSON-RPC options
server=1
rpcuser=myusername
rpcpassword=mypassword
rpcport=8332

# Miscellaneous options
gen=0  # 0 to disable mining, 1 to enable
```

## JSON-RPC Interface

Bitcoin provides a JSON-RPC interface for programmatic access:

- getblockcount: Returns the number of blocks in the longest blockchain
- getconnectioncount: Returns the number of connections to other nodes
- getdifficulty: Returns the proof-of-work difficulty
- getgenerate: Returns if the server is generating coins
- setgenerate: Sets if the server is generating coins
- gethashespersec: Returns a recent hashes per second performance metric
- getinfo: Returns an object containing various state info
- getnewaddress: Returns a new Bitcoin address for receiving payments
- getreceivedbyaddress: Returns the total amount received by an address
- getblock: Returns information about the given block
- sendtoaddress: Sends an amount to a given address
- stop: Stops the Bitcoin server
- validateaddress: Checks if the given address is valid

## Genesis Block

The genesis block (the first block in the blockchain) contains a special message:

```
"The Times 03/Jan/2009 Chancellor on brink of second bailout for banks"
```

This refers to a headline in The Times newspaper and serves as both a timestamp and a comment on the purpose of Bitcoin's creation.

## Monetary Policy

- Initial block reward: 50 BTC
- Block reward halving: Every 210,000 blocks (approximately 4 years)
- Maximum supply: 21 million BTC

## License

Copyright (c) 2009 Satoshi Nakamoto

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
