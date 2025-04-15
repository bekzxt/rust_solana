# Assignment 2.2 rust_solana

## Prerequisites
- Rust (install via [rustup](https://rustup.rs/))
- Solana CLI (install via [official guide](https://solana.com/docs/intro/installation))
- Git

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/solana-hello-world.git
   cd solana-hello-world
   Here's the requested section in code format for your README.md:
## Build and Deployment
### Build the program:
```bash
cargo build-bpf
```
### Deployment steps:
1. Configure Solana CLI for devnet:
```bash
solana config set --url devnet
```
2. Deploy the program:
```bash
solana program deploy ./target/deploy/untitled19.so
```

![image](https://github.com/user-attachments/assets/9af3124a-d782-43a6-8775-bbc0037cafbc)
Successful deployment output showing program ID

![image](https://github.com/user-attachments/assets/eb2db2a8-4ec7-4d26-a5e4-1374b3f4d3b0)
Solana CLI version and wallet address verification

# Cargo.toml
<pre> toml [package] 
  name = "untitled19" 
  version = "0.1.0" 
  edition = "2021" 
  
  [lib] 
  crate-type = ["cdylib"] 
  
  [dependencies] 
  solana-program = "1.18.26" 
  
  [features] 
  no-entrypoint = [] </pre>

## Smart Contract Code
The core functionality is in src/lib.rs:
```use solana_program::{
    account_info::AccountInfo,
    entrypoint,
    entrypoint::ProgramResult,
    pubkey::Pubkey,
    msg,
};

#[cfg(not(feature = "no-entrypoint"))]
entrypoint!(process_instruction);

fn process_instruction(
    _program_id: &Pubkey,
    _accounts: &[AccountInfo],
    _instruction_data: &[u8],
) -> ProgramResult {
    msg!("Hello from my custom Solana program!");
    Ok(())
}
```


## Team Members
Amirov Bekzat, Ermukhanov Daulet, Zhumakanova Asselya.

## Resources
- [Solana Documentation](https://solana.com/docs)
- [Rust Documentation](https://doc.rust-lang.org/book/)
- [Solana CLI Reference](https://solana.com/docs/cli)
