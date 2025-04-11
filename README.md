# Solana Smart Contract - Hello World

This project demonstrates the process of setting up, developing, and deploying a simple "Hello World" smart contract on Solana using Rust. The steps cover everything from installing necessary tools, creating a Solana wallet, to writing and deploying the smart contract.

## Prerequisites

Before you start, make sure you have the following installed:

- [Rust](https://www.rust-lang.org/tools/install)
- [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)

## Step 1: Install Solana CLI and Generate Keypair

First, you need to install the Solana CLI. This allows you to interact with the Solana blockchain from the command line. After installation, generate a new keypair and configure your environment to use the Solana Devnet.

1. Install Solana CLI:
```bash
 sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
```

2. Generate a keypair:
```bash
   solana-keygen new --force
```

3. Set your Solana environment to Devnet:
```bash
   solana config get 
   ```

   This sets up your Solana environment to interact with the Devnet.

   ![Generate Keypair and Set Devnet](https://github.com/user-attachments/assets/86d4fcad-6d52-48aa-8a17-5ac84f58de3c)

## Step 2: Run Local Validator, View Wallet Address, and Request an Airdrop of SOL

1. Run a local Solana validator:

   ```bash
   solana-test-validator
   ```

2. View your wallet address:

   ```bash
   solana address
   ```

   This will display your wallet address on the terminal.

3. Request an airdrop of SOL to fund your wallet:

   ```bash
   solana airdrop 2
   ```

   This will send 2 SOL to your wallet address.

   ![Run Local Validator](https://github.com/user-attachments/assets/b4543f19-f4c9-4e33-aa5b-fa49611b3293)

   ![Request Airdrop](https://github.com/user-attachments/assets/c4f1806a-8a9b-4c34-b7e7-328dad963bc6)

## Step 3: Create Solana Smart Contract

### 3.1: Initialize Cargo Library and Update `Cargo.toml`

Start by initializing a new Rust library using Cargo, and then update the `Cargo.toml` file to include the required dependencies.

1. Initialize the new library:

   ```bash
   cargo new smart-contract --lib
   ```

2. Navigate into the `smart-contract` directory and open `Cargo.toml`:

   Add the following dependencies for Solana development:

   ```toml
   [dependencies]
   solana-program = "1.18.2"
   ```

   ![Cargo Initialization](https://github.com/user-attachments/assets/e495e4df-d554-4f0d-9c14-56b231e7e407)

   ![Update Cargo.toml](https://github.com/user-attachments/assets/b45378cd-7cee-48a5-a236-58868b1bc65c)

### 3.2: Write the Smart Contract

Next, write the smart contract in Rust that logs a "Hello, World!" message when invoked. Here's an example code snippet:

   ![Smart Contract Code](https://github.com/user-attachments/assets/f5b6894b-99a0-461c-8073-b364cc9cee57)

### 3.3: Install SBF (Solana BPF SDK) for Compiling Smart Contract on Rust

To compile the smart contract, you need to install the Solana BPF SDK. This will allow you to build the contract for the Solana blockchain.

1. Install the Solana BPF SDK:

   ```bash
   cargo build-sbf
   ```
    ![SBF Installation](https://github.com/user-attachments/assets/244917d3-7ade-408b-904b-875c78a24e55)

2. Once installed, you can build the contract using:

   ```bash
   cargo build --release
   ```

   This command will compile your contract into a `.so` file ready for deployment.

   ![Build SBF](https://github.com/user-attachments/assets/c57a15b6-af5b-47d5-ae77-6a6edc2eb436)

## Step 4: Deploy the Program to Solana

After successfully building the smart contract, deploy it to Solana's Devnet using the following command:

```bash
solana program deploy target/deploy/smart_contract.so
```

This will deploy the smart contract to the Solana blockchain and provide the Program ID.

   ![Final SBF Setup](https://github.com/user-attachments/assets/462195cb-7319-4549-9fe6-365f1989aeec)

## Project Structure

- `src/` — Contains the source code of the Rust program.
- `Cargo.toml` — Configuration file for the project.
- `target/` — Compiled files, including the `.so` file ready for deployment.

## License

This project is licensed under the [MIT License](LICENSE).

Copyright (c) 2016-2025 Astana IT University

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
