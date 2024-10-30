*Using [[Rust for C++ Developers]] and [[Substrate]].*

## Setting Up Your Dev Environment

First things first, you'll need these tools installed:
```bash
# For your Mac:
curl https://sh.rustup.rs -sSf | sh
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
rustup update stable
cargo install --git https://github.com/alexcrichton/wasm-gc

# Grab the starter code:
git clone https://github.com/substrate-developer-hub/utxo-workshop.git
git fetch origin workshop:workshop
git checkout workshop
```

## Understanding UTXO: The Building Blocks

Think of UTXOs like a special kind of traveller's cheque:
- You've got to spend the whole thing
- Only the rightful owner can spend it
- You get change back as a new cheque

### Core Components from the Tutorial
```rust
/// The main transaction structure
#[derive(PartialEq, Eq, PartialOrd, Ord, Default, Clone, Encode, Decode, Hash, Debug)]
pub struct Transaction {
    pub inputs: Vec<TransactionInput>,
    pub outputs: Vec<TransactionOutput>,
}

/// What you're spending
#[derive(PartialEq, Eq, PartialOrd, Ord, Default, Clone, Encode, Decode, Hash, Debug)]
pub struct TransactionInput {
    pub outpoint: H256,
    pub sigscript: H512,
}

/// What you're creating
#[derive(PartialEq, Eq, PartialOrd, Ord, Default, Clone, Encode, Decode, Hash, Debug)]
pub struct TransactionOutput {
    pub value: Value,
    pub pubkey: H256,
}
```

## Building the Chain

### 1. Setting Up Storage
Here's how we track UTXOs on the blockchain:
```rust
decl_storage! {
    trait Store for Module<T: Trait> as Utxo {
        /// All valid unspent transaction outputs are stored here
        UtxoStore build(|config: &GenesisConfig| {
            config.genesis_utxos
                .iter()
                .cloned()
                .map(|u| (BlakeTwo256::hash_of(&u), u))
                .collect::<Vec<_>>()
        }): map H256 => Option<TransactionOutput>;

        /// Total reward value for validators
        pub RewardTotal get(reward_total): Value;
    }
}
```

### 2. Transaction Processing
The real yakka happens in the spend function:
```rust
pub fn spend(_origin, transaction: Transaction) -> DispatchResult {
    let transaction_validity = Self::validate_transaction(&transaction)?;
    Self::update_storage(&transaction, transaction_validity.priority as u128)?;
    Self::deposit_event(Event::TransactionSuccess(transaction));
    Ok(())
}
```

### 3. Security Measures
Bonza security checks from the tutorial:
```rust
pub fn validate_transaction(transaction: &Transaction) -> Result<ValidTransaction, &'static str> {
    // Basic checks
    ensure!(!transaction.inputs.is_empty(), "no inputs");
    ensure!(!transaction.outputs.is_empty(), "no outputs");

    // Check for duplicates
    let input_set: BTreeMap<_, ()> = transaction.inputs.iter().map(|input| (input, ())).collect();
    ensure!(input_set.len() == transaction.inputs.len(), "each input must only be used once");

    // More validation logic...
}
```

## Testing Your Blockchain

### Setting Up the Test Environment
```rust
fn new_test_ext() -> sp_io::TestExternalities {
    let keystore = KeyStore::new();
    let alice_pub_key = keystore.write().sr25519_generate_new(SR25519, Some(ALICE_PHRASE)).unwrap();

    // Set up the genesis block with Alice having 100 coins
    let mut t = system::GenesisConfig::default()
        .build_storage::<Test>()
        .unwrap();
    // More setup code...
}
```

### Writing Your First Test
```rust
#[test]
fn test_simple_transaction() {
    new_test_ext().execute_with(|| {
        let alice_pub_key = sp_io::crypto::sr25519_public_keys(SR25519)[0];
        // Test transaction logic...
    });
}
```

## Handling Race Conditions

One of the trickier bits is handling transactions that depend on each other. The tutorial shows how to sort this with the transaction queue:
```rust
impl sp_transaction_pool::runtime_api::TaggedTransactionQueue<Block> for Runtime {
    fn validate_transaction(tx: <Block as BlockT>::Extrinsic) -> TransactionValidity {
        // Handle UTXO transactions specially
        if let Some(&utxo::Call::spend(ref transaction)) = 
            IsSubType::<utxo::Module<Runtime>, Runtime>::is_sub_type(&tx.function) {
            // Validation logic...
        }
        // Default handling for other transaction types
        Executive::validate_transaction(tx)
    }
}
```

## Deploying Your Chain

Final steps from the tutorial:
1. Build your release:
```bash
# Set up Wasm build environment
./scripts/init.sh

# Build it all
cargo build --release
```

2. Fire it up:
```bash
./target/release/utxo-workshop --dev

# Need a fresh start?
./target/release/utxo-workshop purge-chain --dev
```

## Top Tips for Blockchain Dev

1. **Security First, Mate**
   - Test everything thoroughly
   - Get your code reviewed
   - Think about all the ways someone might try to rort the system

2. **Keep It Clean**
   - Document your code
   - Use clear naming
   - Break things into manageable chunks

3. **Think About Scale**
   - How will it handle loads of users?
   - What happens when the chain gets massive?
   - How can you upgrade it later?

## Common Dramas to Watch For

1. **Race Conditions**
   - Transactions arriving out of order
   - Multiple people trying to spend the same UTXO
   - Network delays

2. **Resource Management**
   - Storage growth
   - Network bandwidth
   - Processing power

3. **User Experience**
   - Transaction confirmation times
   - Fee structures
   - Error handling


See also:
- [Building Your Own Blockchain Using Rust and Substrate](https://hackernoon.com/building-a-blockchain-in-rust-and-substrate-a-step-by-step-guide-for-developers-kc223ybp)