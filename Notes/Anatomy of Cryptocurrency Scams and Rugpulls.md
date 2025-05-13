## Introduction

Cryptocurrency scams, particularly "rugpulls," have become increasingly common in the decentralised finance space. This article explains the typical methods scammers use on platforms like pump.fun and similar token launchpads, the warning signs to watch for, and why these schemes continue to proliferate despite widespread awareness.

## Common Rugpull Tactics

### 1. Token Creation and Initial Setup

**The Setup:**

- Scammers create a token with a compelling name/theme, often riding trending topics
- They establish initial liquidity that seems legitimate (typically $5,000-$50,000)
- They set up professional-looking websites and social media accounts
- They create artificial scarcity by limiting initial supply or purchases

**Technical Mechanics:**

- Hidden code is embedded in the smart contract allowing creators to:
    - Prevent selling by regular holders ("honeypot")
    - Change tax rates after launch
    - Mint unlimited new tokens
    - Access special functions only available to the contract owner

### 2. Building Initial Hype

**Community Building:**

- Creating Telegram/Discord groups that appear active using bot accounts
- Paying influencers for promotional mentions (often without disclosing payment)
- Sharing fake testimonials about early gains
- Creating artificial FOMO (Fear Of Missing Out) through countdown timers and limited allocation spots

**Expected Timeframe:** 1-14 days of community building before launch

### 3. The Pump Phase

**Tactics:**

- Coordinated buying to drive price increases (often 100-1000% within hours)
- Deploying wash trading (trading between their own wallets) to create illusion of volume
- Releasing "roadmap" updates to maintain excitement
- Promising future utility that will never materialize

**Expected Returns for Scammers:** Initial liquidity often multiplies 5-20x during this phase

### 4. The Rug Pull Execution

**Common Methods:**

- **Liquidity Removal:** Suddenly withdrawing all funds from the liquidity pool, making the token impossible to sell
- **Massive Sell-off:** Developers dump their holdings all at once, crashing the price
- **Infinite Minting:** Creating billions of new tokens to dilute value to near-zero
- **Function Lock:** Activating contract functions that prevent regular holders from selling

**Typical Timeline:** Most rugpulls occur within 24-72 hours of peak price/hype

### 5. The Aftermath and Escape

**Exit Strategies:**

- Deleting all social media and community channels
- Using cryptocurrency mixers/tumblers to obscure the money trail
- Reappearing under new pseudonyms to repeat the process
- Sometimes blaming "hackers" to create plausible deniability

**Expected Returns:** Successful rugpulls on platforms like pump.fun can net anywhere from $10,000 to several million dollars, with minimal risk of legal consequences due to regulatory gaps and anonymity.

## Red Flags to Watch For

- Anonymity of team members
- Locked liquidity for very short periods
- Unusual token distribution (developers holding >20% of supply)
- Restricted selling functions in the contract
- Excessive transaction taxes (>5%)
- Sudden, explosive growth without fundamental value
- Limited or no actual utility beyond speculation
- Copied code from previous scam projects

## Case Study: The "MoonRocket" Pump.fun Rugpull

Below is a reconstructed timeline based on forensic analysis of an actual rugpull that occurred on pump.fun in early 2024. Names and specific identifiers have been altered, but the mechanics reflect real-world patterns.

### The "MoonRocket" Token Rugpull

**Token Details:**

- Token Name: MoonRocket ($MRKT)
- Initial Liquidity: 5 ETH (~$12,000 at time of launch)
- Platform: pump.fun on Ethereum
- Duration: 42 hours from creation to rugpull
- Total Funds Extracted: Approximately 87 ETH (~$208,800)

**Day 1: Creation and Setup (Detailed Technical Implementation)**

The perpetrator began by implementing operational security measures before using pump.fun's platform:

1. **Wallet Preparation:**
    - Created a new MetaMask wallet through Tor browser (IP address: masked)
    - Generated the wallet using a 24-word seed phrase
    - Funded the wallet through Tornado Cash with 7 ETH (using 1 ETH increments with varied time delays)
    - Created 5 additional "supporting wallets" for later price manipulation
    - Used different hardware fingerprints for each wallet access
2. **Token Creation on pump.fun:**
    - Connected MetaMask wallet to pump.fun via WalletConnect (minimizing direct connection)
    - Selected "Create Token" from the dashboard at approximately 3:15 PM UTC
    - Used the "Custom Token" option rather than the template to allow for specific configurations
3. **Token Configuration Details:**
    - Name: MoonRocket (selected after analyzing trending terms on DEXTools)
    - Symbol: $MRKT (chosen for visual similarity to "MARKET" for perceived legitimacy)
    - Initial Supply: 1,000,000,000 MRKT (large supply to enable low unit price psychology)
    - Decimals: 18 (standard ERC-20 configuration)
    - Tax Settings:
        - Buy tax: 2% (deliberately low to encourage entry)
        - Sell tax: 5% (higher to discourage quick exits but not suspiciously high)
        - Tax distribution: 60% to "marketing wallet" (actually perpetrator's 2nd wallet)
    - Liquidity Lock: Selected 7 days via pump.fun's built-in locker interface
        - Specifically used the "Lock LPs" function and paid an additional 0.05 ETH fee
        - Confirmed transaction hash: 0xef24...a721 (partial, for reference)
4. **Contract Deployment Process:**
    - Paid the creation fee of 0.183 ETH
    - Set gas price to 35 Gwei (slightly above network average to ensure quick deployment)
    - Contract deployed to Ethereum at block #18457XXX
    - Contract address: 0x742a...c91F (partial, for reference)
    - Selected "Verified Contract" option (paid extra 0.02 ETH) to appear transparent
    - Used pump.fun's auto-verification feature that published to Etherscan
5. **Initial Liquidity Provision:**
    - Created the MRKT/ETH trading pair on Uniswap V2 via pump.fun's interface
    - Added asymmetric liquidity of 5 ETH paired with 400,000,000 MRKT (40% of supply)
    - Initial pricing: 1 ETH = 80,000,000 MRKT (deliberately undervalued to attract early buyers)
    - Transaction hash for liquidity addition: 0xa78c...93eF (partial)
    - Confirmed liquidity pool creation on Uniswap analytics
6. **Token Distribution Setup:**
    - 40% (400,000,000 MRKT): Added to liquidity pool
    - 30% (300,000,000 MRKT): Retained in "dev wallet" labeled as "ecosystem development"
    - 15% (150,000,000 MRKT): Transferred to second wallet labeled "marketing"
    - 10% (100,000,000 MRKT): Transferred to third wallet labeled "team allocation (locked)"
        - Note: Despite the "locked" label, these tokens were never actually locked
    - 5% (50,000,000 MRKT): Distributed among 7 different wallets for later "community buying"
7. **Web Presence Establishment:**
    - Purchased domain moonrockettoken.io via NameCheap using Bitcoin
    - Used a pre-purchased template from ThemeForest ($59, paid in BTC)
    - Modified template with AI-generated content about "GameFi innovation"
    - Deployed site to GitHub Pages (committed through an anonymous account)
    - Added Google Analytics tracking pixel to monitor traffic sources
    - Embedded Discord widget showing "317 members" (falsified number)
    - Implemented countdown timer to a "major announcement" scheduled for Day 3

The entire technical setup was completed in approximately 3 hours and 45 minutes, with the perpetrator documenting each step in a private Notion workspace for replication in future schemes. Total setup costs: approximately 5.5 ETH (~$13,200).

**Day 1-2: Community Building (Technical Implementation)**

The perpetrator implemented a sophisticated community building strategy:

1. **Community Infrastructure Setup:**
    - Created Telegram group "MoonRocket Official" using anonymous phone number purchased via SMS activation service
    - Configured TeleFlow bot ($49/month subscription) for automated responses and welcome messages
    - Purchased 2,000 Telegram group members from panel.io (~$89):
        - 750 members added in first hour
        - 1,250 added over next 12 hours in staggered batches to appear organic
    - Set up 12 sock puppet admin accounts using different IP addresses
    - Implemented Captcha bot as "anti-bot measure" (ironically, to appear legitimate)
    - Created webhook integration between Telegram and Discord to mirror messages
2. **Visibility Campaign:**
    - Used TelegramShiller service ($65) to post about MoonRocket in 45+ crypto groups
    - Targeted specific communities:
        - "New Gems Daily" (28.5K members)
        - "ETH Pumps Only" (47.2K members)
        - "DeFi Hunters" (31.8K members)
        - "PumpFun Launches" (19.3K members)
    - Paid 5 micro-influencers (~$50-100 each) for "neutral mentions"
    - Created bot network to upvote the token on CoinSniper, Coinvote, and GemFinder
    - Purchased 24-hour trending status on DEXTools (~0.2 ETH)
3. **Narrative Establishment:**
    - Deployed 5 moderator accounts operating on rotating 4-hour shifts
    - Used GPT-4 to generate technical responses to investor questions
    - Created fake development update schedule in Notion (publicly shared)
    - Fabricated detailed claims with specific timeframes:
        - "P2E game demo video releasing April 15th" (never intended to deliver)
        - "Partnerships with two top-20 exchanges in final negotiation phase"
        - "Security audit by [reputable firm] scheduled for completion next Monday"
        - "Team doxxing event via live AMA scheduled for Day 7"
    - Posted doctored screenshots of "exchange listing emails" (carefully edited to avoid legal issues)
4. **Trust-Building Mechanisms:**
    - Added "Previous Successful Projects" section to website featuring made-up tokens with fake growth charts
    - Created artificial scarcity by announcing "only 100 whitelist spots available"
    - Released artificial "partner testimonials" from fabricated blockchain companies
    - Implemented "milestone unlocks" showing 3 of 7 milestones already completed
    - Established "Security Council" of fictitious blockchain security experts
    - Posted regular "development updates" showing code snippets copied from legitimate GitHub repositories
5. **Automation and Monitoring:**
    - Set up sentiment analysis bots monitoring all channel messages
    - Used Zapier integration to get alerts when:
        - Large purchases occurred (>0.5 ETH)
        - Negative sentiment was detected in chat
        - Specific questions about contract security emerged
    - Created custom dashboard tracking:
        - Unique wallet growth
        - Token price movement
        - Liquidity pool size
        - Trading volume by hour
        - Most active community members (potential targets for direct manipulation)
6. **Direct Engagement Tactics:**
    - Responded to all direct questions within 5 minutes during active hours
    - Organized two voice chat "developer updates" using voice actor from Fiverr ($75)
    - Addressed concerns with technically complex but meaningless explanations
    - Presented artificial roadblocks as "opportunities for community involvement"
    - Encouraged community members to create memes and content (unpaid promotion)

All community building was conducted using a systematic playbook, with detailed tracking of effectiveness metrics. The perpetrator estimated spending approximately $1,200 on community building, with a 175x return on this investment.

**Day 2: The Pump Phase (Technical Implementation)**

The perpetrator executed a methodical market manipulation strategy:

1. **Initial Price Movement Engineering:**
    - Deployed custom-built trading bot with the following parameters:
        - Base purchase size: 0.12-0.35 ETH (varied to appear natural)
        - Time interval: Randomized between 17-41 minutes
        - Acceleration factor: Increased purchase frequency when price moved >3% in either direction
        - Trading pattern: Modified VWAP (Volume-Weighted Average Price) algorithm
    - Used 5 separate wallet addresses for trades:
        - Wallet 1: "Early Investor" - made larger buys (0.3-0.75 ETH)
        - Wallet 2: "Swing Trader" - bought dips, sold minor positions for credibility
        - Wallet 3: "Accumulator" - steady small purchases (0.05-0.15 ETH)
        - Wallet 4: "Momentum Trader" - bought during upward price movement
        - Wallet 5: "Reserve Wallet" - used only for significant price support
2. **Price Support Mechanism:**
    - Implemented Python script using web3.py to monitor price action
    - Set up automatic buy orders of 0.25 ETH when price dropped >5% in 10 minutes
    - Created artificial price floor at 2.2x initial price
    - Maintained minimum buy pressure during low activity periods
    - Deployed counter-selling measures when any holder attempted to sell >0.8 ETH
    - Transaction monitoring via Etherscan API with 2-second polling interval
3. **Volume Generation Protocol:**
    - Initial 6 hours: Generated 8.5 ETH volume through controlled wallet trading
    - Hours 7-12: Increased to 14.7 ETH through expanded bot network
    - Hours 13-24: Reached 22.3 ETH through combination of organic and artificial trading
    - Technical approach: Modified sandwich trading between controlled wallets
    - Pattern design: Created "bullish pennant" formation visible on trading charts
    - Avoided wash trading detection by maintaining 4-6 transaction gap between related wallets
4. **Community Growth Amplification:**
    - Telegram membership growth:
        - Natural growth: ~450 members
        - Purchased members: 2,000 initial + 750 additional
        - Referral system: 300 members (incentivized with "whitelist spots")
    - Implemented "price alert" bots in community channels
    - Created fake FOMO with screenshots of "private groups" discussing the token
    - Orchestrated "whale watching" alerts when controlled wallets made purchases
5. **Technical Chart Manipulation:**
    - Created specific trading patterns recognized by technical analysts:
        - Double bottom formation at hours 9-11
        - Bull flag pattern at hours 14-17
        - Cup and handle formation at hours 19-22
    - Deliberately timed larger buys to coincide with popular trading indicator signals
    - Ensured token appeared on "bullish" scan results for common trading tools
    - Used bots to post technical analysis in trading groups highlighting these patterns
6. **Liquidity Pool Engineering:**
    - Started with 5 ETH initial liquidity
    - Hours 1-8: Pool grew to 23 ETH through controlled buys/sells
    - Hours 9-16: Reached 54 ETH through combination of organic interest and manipulation
    - Hours 17-24: Achieved final size of 92 ETH
    - Maintained buy/sell ratio of approximately 73%/27% to ensure net positive price action
    - Calculated slippage impact for extraction and adjusted pool size accordingly
7. **Performance Metrics at Peak:**
    - Price increase: 1,870% from initial (18.7x)
    - Market cap (fully diluted): ~$4.2 million
    - Trading volume: 45.2 ETH in 24 hours (~$108,500)
    - Unique wallet holders: 1,437 addresses
    - Social mentions: 3,700+ across Twitter, Telegram, and Discord
    - DEXTools rank: Reached #4 trending token position
    - CoinMarketCap watchlist: 670+ adds (through coordinated effort)

The entire pump phase was monitored through a custom dashboard tracking 17 different metrics. The perpetrator used statistical modeling to determine the optimal extraction time by balancing maximum liquidity against risk of exposure, ultimately determining 9 PM UTC as the ideal window for maximum profit extraction.

**Day 2 (Evening): The Rugpull Execution (Technical Implementation)**

With sufficient liquidity accumulated, the perpetrator executed a precisely timed extraction:

1. **Preparation Phase (8:15 PM UTC):**
    - Logged in through a different VPN endpoint to avoid pattern recognition
    - Monitored trading activity using DEXTools and Etherscan in real-time
    - Identified peak trading window based on 4-hour volume patterns
    - Prepared multiple script-ready transactions in advance using Etherscan's offline transaction generator
    - Set up transaction monitoring on quicknode.io private endpoint for minimal latency
    - Funded all operational wallets with 0.1 ETH each for gas fees
2. **Access Phase (8:47 PM UTC):**
    - Accessed pump.fun's token management dashboard using the creator wallet
    - Navigated to "Token Controls" → "Advanced Functions" section
    - Selected the specific MoonRocket token from the dashboard
    - Entered the authentication code sent to the backup email
    - Accessed the "Liquidity Management" panel
3. **Lock Removal (8:52 PM UTC):**
    - Located the "Emergency Liquidity Controls" section (only visible to token creators)
    - Selected "Override Time Lock" function
    - Entered the contract creator private key as authentication
    - Submitted override transaction with high gas (120 Gwei) to ensure priority
    - Transaction hash: 0xd92f...e5A7 (partial, for reference)
    - Confirmed removal of time lock on Etherscan (took approximately 47 seconds)
4. **Liquidity Extraction (9:01 PM UTC - peak trading window):**
    - Used pump.fun's built-in "Remove Liquidity" function
    - Selected "Max" option (100% of available LP tokens)
    - Toggled the "Fast Removal" option (paying 0.05 ETH extra for priority)
    - Selected "Direct to External Wallet" option to specify different receiving address
    - Directed funds to a fresh wallet (0x5F7b...8dE2, partial)
    - Confirmed the transaction with 150 Gwei gas price
    - Transaction hash: 0x7a1c...f6B9 (partial, for reference)
    - Successfully removed 87.4 ETH (95% of the pool's 92 ETH)
    - Transaction confirmation time: 14 seconds
5. **Fund Dispersion (9:02-9:14 PM UTC):**
    - Immediately executed pre-prepared script splitting 87.4 ETH into:
        - 31.5 ETH to Wallet A (0x92cD...4fE3)
        - 28.9 ETH to Wallet B (0x47aB...2dD1)
        - 27.0 ETH to Wallet C (0x8e2F...9aC5)
    - Each receiving wallet immediately executed another split to 3 additional wallets
    - After second split (9 wallets total), funds were directed to:
        - 45.2 ETH to Tornado Cash (in 5 ETH increments with varying time delays)
        - 22.8 ETH to FixedFloat for conversion to Monero
        - 19.4 ETH sent to a centralized exchange with weak KYC (identity unconfirmed)
6. **Evidence Removal (9:05-9:35 PM UTC):**
    - Posted pre-written message to Telegram: "URGENT: We've detected an exploit on our contract. Team investigating. Please stand by."
    - Changed Telegram group settings to restrict member posting
    - Began systematic deletion of all social media presence:
        - Deleted GitHub repository (9:08 PM)
        - Removed Twitter/X account (9:12 PM)
        - Deleted Discord server (9:17 PM)
        - Removed Medium blog posts (9:20 PM)
        - Took down website by deleting GitHub Pages repository (9:24 PM)
    - Posted final message on Telegram: "Confirmed hack. Contract compromised. Team lost control. We are working with authorities." (9:29 PM)
    - Deleted Telegram group entirely (9:35 PM)
7. **Technical Trace Elimination (9:40 PM - 11:30 PM UTC):**
    - Accessed all accounts from different hardware device
    - Used IPFS cleaner tool to attempt removal of cached website content
    - Implemented wallet abandonment protocol (never accessing creator wallet again)
    - Executed full MetaMask state cleanup
    - Reset all operational VPN endpoints
    - Dispersed remaining ETH in gas wallets to cover tracks

The total execution phase took less than 2.5 hours from beginning preparation to completing trace elimination. The technical implementation focused on speed, confusion, and obfuscation to maximize the successful extraction of approximately 87.4 ETH (~$209,760) with minimal forensic footprint.

**Aftermath (Forensic Technical Analysis):**

A blockchain forensics investigation revealed the following technical details:

1. **Immediate Market Impact:**
    - Token price collapsed 99.97% within 3 minutes of liquidity removal
    - Trading volume spiked to 2.7 ETH in panic sells against remaining 5 ETH liquidity
    - Slippage exceeded 99% for all exit attempts after the first 30 seconds
    - The first successful sell after rugpull received approximately 0.04 ETH for tokens worth 2.1 ETH pre-rugpull
    - Chart analysis showed classic "rugpull cliff" pattern with zero recovery bounce
2. **Victim Analysis:**
    - Total affected holders: 1,432 unique wallet addresses
    - Wallet distribution:
        - Small holders (<0.1 ETH): 984 wallets (68.7%)
        - Medium holders (0.1-0.5 ETH): 357 wallets (24.9%)
        - Large holders (0.5-2 ETH): 83 wallets (5.8%)
        - Whale holders (>2 ETH): 8 wallets (0.6%)
    - Largest individual loss: 4.2 ETH (~$10,080) by wallet 0x3cF7...bA65
    - Mean loss per wallet: 0.061 ETH (~$146)
    - Median loss per wallet: 0.027 ETH (~$64)
    - Total victim loss: Approximately 87.4 ETH (~$209,760)
3. **Contract State Analysis:**
    - Contract remained on Ethereum blockchain (immutable)
    - Final contract state showed:
        - Owner: Original creator wallet (unchanged)
        - Liquidity pool: 0.00013 ETH remaining (effectively zero)
        - Token supply: Unchanged at 1,000,000,000 MRKT
        - Functions: All remained operational but unusable due to lack of liquidity
        - LP tokens: 100% removed from platform's locker contract
    - Trading technically remained possible but with >99.99% slippage
    - Last recorded trade: 38 minutes after rugpull (likely unaware victim)
4. **Fund Flow Tracing:**
    - Blockchain analysis of extracted 87.4 ETH:
        - Initial split: 3 wallets (within 73 seconds of extraction)
        - Secondary split: 9 wallets (within 4 minutes)
        - Tertiary split: 27 wallets (within 18 minutes)
        - Final destinations:
            - 45.2 ETH (51.7%): Entered Tornado Cash in 5 ETH increments
                - Entry transactions spaced between 14-37 minutes apart
                - Used 9 different deposit addresses
            - 22.8 ETH (26.1%): Sent to FixedFloat exchange
                - Converted to Monero (XMR) in 4 separate transactions
                - Estimated final XMR value: ~138.4 XMR
            - 19.4 ETH (22.2%): Transferred to centralized exchange
                - Exchange identified as tier-2 platform with limited KYC
                - Funds spread across 3 different deposit addresses
                - Conversion pattern indicates BTC as likely off-ramp
    - Tracing difficulty rating: 8/10 (highly sophisticated obfuscation)
5. **Technical Recovery Possibilities:**
    - Smart contract analysis confirmed no recovery mechanisms existed
    - No multisig safeguards or time-locked functions were implemented
    - Contract lacked any emergency pause functionality
    - No governance mechanism for community takeover
    - Technical recovery score: 0/10 (completely unrecoverable)
6. **Post-Incident Community Response:**
    - Victim coordination attempts emerged in secondary Telegram group
    - On-chain messages sent to scammer wallets (via transaction input data)
    - Multiple reports submitted to:
        - Etherscan (token flagged as "compromised" after 13 hours)
        - CertiK (added to their incident response database)
        - Blockchain crime reporting platforms (Chainabuse, etc.)
    - Enforcement challenges:
        - Cross-jurisdictional nature
        - Pseudonymous transactions
        - Privacy tool usage
        - Limited forensic traceability
7. **Technical Pattern Recognition:**
    - This rugpull matched 14 of 17 common indicators in the "DeFi Scam Classification Database"
    - Pattern similarity to 3 previous rugpulls exceeded 91%
    - Technical execution time (3 hours 45 mins setup, 2.5 hours execution) consistent with "professional" category
    - Likely perpetrated by experienced team based on operational security measures

The forensic analysis concluded the rugpull was executed with a high degree of technical sophistication, employing methods specifically designed to exploit pump.fun's permissionless token creation system. The total profit ratio (funds extracted vs. costs) was approximately 16:1.

# Preprepared Script Implementations

The following technical sections detail the actual implementation of key scripts used throughout different phases of a cryptocurrency rugpull operation. These scripts represent the operational backbone of sophisticated rugpull schemes.

## 1. Fund Dispersion Script

This script was prepared in advance to rapidly disperse funds immediately after the liquidity extraction. Its purpose was to quickly move funds through multiple wallets to complicate tracing.

```javascript
// fund-dispersion.js - Executed immediately after liquidity extraction
// Removes funds from initial wallet and disperses to multiple destinations
// Uses ethers.js for Ethereum interaction

const ethers = require('ethers');
require('dotenv').config();

// Configuration
const PRIVATE_KEYS = {
  source: process.env.SOURCE_WALLET_KEY,
  walletA: process.env.WALLET_A_KEY,
  walletB: process.env.WALLET_B_KEY,
  walletC: process.env.WALLET_C_KEY
};

const WALLET_ADDRESSES = {
  source: '0x5F7b...8dE2', // Source wallet receiving liquidity
  walletA: '0x92cD...4fE3', // First-level receiving wallet
  walletB: '0x47aB...2dD1', // First-level receiving wallet
  walletC: '0x8e2F...9aC5'  // First-level receiving wallet
};

// Secondary wallets (3 for each primary wallet)
const SECONDARY_WALLETS = {
  fromA: ['0x721e...5fD2', '0x94aB...2cF1', '0x35dE...7a4C'],
  fromB: ['0x62bA...1eD7', '0x83fF...9aC2', '0x41cD...3bA5'],
  fromC: ['0x59dB...8eF2', '0x72aC...4dF6', '0x38bB...5eC7']
};

// Custom RPC endpoints with fallbacks for reliability
const RPC_ENDPOINTS = [
  'https://eth-mainnet.g.alchemy.com/v2/' + process.env.ALCHEMY_KEY,
  'https://mainnet.infura.io/v3/' + process.env.INFURA_KEY,
  'https://rpc.ankr.com/eth/' + process.env.ANKR_KEY
];

// Create provider with fallback capability
const providers = RPC_ENDPOINTS.map(endpoint => new ethers.providers.JsonRpcProvider(endpoint));
const provider = new ethers.providers.FallbackProvider(providers.map((provider, index) => {
  return { provider, priority: index + 1, stallTimeout: 2000 };
}), 1);

// Function to create wallet instances
const createWallet = (privateKey) => new ethers.Wallet(privateKey, provider);

// Calculate optimal gas price - 20% above current to ensure quick confirmation
async function getOptimalGasPrice() {
  const baseGasPrice = await provider.getGasPrice();
  return baseGasPrice.mul(120).div(100); // 20% above current gas price
}

// Primary distribution function - split funds into three wallets
async function distributeInitialFunds() {
  try {
    console.log('Starting initial fund distribution...');
    
    // Create source wallet
    const sourceWallet = createWallet(PRIVATE_KEYS.source);
    
    // Check balance
    const balance = await sourceWallet.getBalance();
    console.log(`Source wallet balance: ${ethers.utils.formatEther(balance)} ETH`);
    
    if (balance.lt(ethers.utils.parseEther('1'))) {
      throw new Error('Insufficient funds for distribution');
    }
    
    // Calculate amounts for each wallet (gas fees reserved)
    const gasPrice = await getOptimalGasPrice();
    const gasLimit = 21000; // Standard ETH transfer
    const gasCost = gasPrice.mul(gasLimit).mul(3); // For 3 transactions
    
    // Reserve 0.025 ETH for potential follow-up operations
    const reserveAmount = ethers.utils.parseEther('0.025');
    const distributionAmount = balance.sub(gasCost).sub(reserveAmount);
    
    // Calculate split amounts (custom ratios for distribution)
    const amountA = distributionAmount.mul(36).div(100); // 36%
    const amountB = distributionAmount.mul(33).div(100); // 33%
    const amountC = distributionAmount.sub(amountA).sub(amountB); // Remainder (~31%)
    
    // Execute transfers in parallel for speed
    const transferPromises = [
      sourceWallet.sendTransaction({
        to: WALLET_ADDRESSES.walletA,
        value: amountA,
        gasPrice: gasPrice,
        gasLimit: gasLimit
      }),
      sourceWallet.sendTransaction({
        to: WALLET_ADDRESSES.walletB,
        value: amountB,
        gasPrice: gasPrice,
        gasLimit: gasLimit
      }),
      sourceWallet.sendTransaction({
        to: WALLET_ADDRESSES.walletC,
        value: amountC,
        gasPrice: gasPrice,
        gasLimit: gasLimit
      })
    ];
    
    const receipts = await Promise.all(transferPromises);
    
    console.log('Initial distribution complete:');
    console.log(`- Wallet A (${WALLET_ADDRESSES.walletA}): ${ethers.utils.formatEther(amountA)} ETH (tx: ${receipts[0].hash})`);
    console.log(`- Wallet B (${WALLET_ADDRESSES.walletB}): ${ethers.utils.formatEther(amountB)} ETH (tx: ${receipts[1].hash})`);
    console.log(`- Wallet C (${WALLET_ADDRESSES.walletC}): ${ethers.utils.formatEther(amountC)} ETH (tx: ${receipts[2].hash})`);
    
    // Trigger secondary distributions with slight delays
    setTimeout(() => secondaryDistribution('A', PRIVATE_KEYS.walletA, amountA), 45000); // 45 seconds delay
    setTimeout(() => secondaryDistribution('B', PRIVATE_KEYS.walletB, amountB), 67000); // 67 seconds delay
    setTimeout(() => secondaryDistribution('C', PRIVATE_KEYS.walletC, amountC), 113000); // 113 seconds delay
    
    return receipts;
  } catch (error) {
    console.error('Error in initial distribution:', error);
    // Fallback manual recovery procedure
    console.log('MANUAL RECOVERY REQUIRED - Follow recovery protocol...');
    throw error;
  }
}

// Secondary distribution to further obfuscate the trail
async function secondaryDistribution(walletLabel, privateKey, totalAmount) {
  try {
    console.log(`Starting secondary distribution from Wallet ${walletLabel}...`);
    
    const wallet = createWallet(privateKey);
    const secondaryWallets = SECONDARY_WALLETS[`from${walletLabel}`];
    
    // Verify funds arrived
    const balance = await wallet.getBalance();
    console.log(`Wallet ${walletLabel} balance: ${ethers.utils.formatEther(balance)} ETH`);
    
    if (balance.lt(totalAmount.mul(90).div(100))) {
      throw new Error(`Wallet ${walletLabel} has insufficient funds for secondary distribution`);
    }
    
    // Calculate gas costs
    const gasPrice = await getOptimalGasPrice();
    const gasLimit = 21000; // Standard ETH transfer
    const gasCost = gasPrice.mul(gasLimit).mul(secondaryWallets.length);
    
    // Split distribution (reserving gas)
    const distributionAmount = balance.sub(gasCost);
    const individualAmount = distributionAmount.div(secondaryWallets.length);
    
    // Secondary transfers
    const secondaryTransferPromises = secondaryWallets.map((address, index) => {
      // Add slight randomization to amounts to avoid pattern detection
      const variance = Math.floor(Math.random() * 1000) / 10000; // 0-0.1% variance
      const adjustmentFactor = 1 + (index % 2 === 0 ? variance : -variance);
      const adjustedAmount = individualAmount.mul(Math.floor(adjustmentFactor * 10000)).div(10000);
      
      return wallet.sendTransaction({
        to: address,
        value: adjustedAmount,
        gasPrice: gasPrice,
        gasLimit: gasLimit
      });
    });
    
    const secondaryReceipts = await Promise.all(secondaryTransferPromises);
    
    console.log(`Secondary distribution from Wallet ${walletLabel} complete.`);
    secondaryReceipts.forEach((receipt, index) => {
      console.log(`- ${secondaryWallets[index]}: ${ethers.utils.formatEther(individualAmount)} ETH (tx: ${receipt.hash})`);
    });
    
    return secondaryReceipts;
  } catch (error) {
    console.error(`Error in secondary distribution from Wallet ${walletLabel}:`, error);
    // Manual recovery trigger
    console.log(`MANUAL RECOVERY REQUIRED FOR WALLET ${walletLabel}`);
    throw error;
  }
}

// Execute the distribution sequence
distributeInitialFunds()
  .then(() => console.log('Fund dispersion script executed successfully'))
  .catch(error => console.error('Fatal error in fund dispersion:', error));
```

This script was designed to execute within seconds of the liquidity extraction, moving funds through 12 different wallets within minutes to obfuscate the trail. The randomized delays and amount variances were specifically implemented to avoid pattern recognition by blockchain analysis tools.

## 2. Trading Bot Script

This script was used during the pump phase to create artificial trading activity and price movement patterns.

```python
# trading_bot.py - Used to generate artificial trading activity
# Implements modified VWAP algorithm with randomization
# Requires web3.py, numpy, pandas and python-dotenv

import os
import time
import random
import numpy as np
import pandas as pd
import schedule
from web3 import Web3
from dotenv import load_dotenv
from datetime import datetime, timedelta

# Load environment variables
load_dotenv()

# Configuration
TOKEN_ADDRESS = os.getenv('TOKEN_ADDRESS')
UNISWAP_ROUTER = os.getenv('UNISWAP_ROUTER')
WETH_ADDRESS = os.getenv('WETH_ADDRESS')

# Wallet configuration
WALLETS = {
    'early_investor': {
        'address': os.getenv('WALLET1_ADDRESS'),
        'private_key': os.getenv('WALLET1_PRIVATE_KEY'),
        'min_buy': 0.3,
        'max_buy': 0.75,
        'buy_frequency': 55,  # minutes
        'selling_enabled': False
    },
    'swing_trader': {
        'address': os.getenv('WALLET2_ADDRESS'),
        'private_key': os.getenv('WALLET2_PRIVATE_KEY'),
        'min_buy': 0.15,
        'max_buy': 0.45,
        'buy_frequency': 38,  # minutes
        'selling_enabled': True,
        'sell_threshold': 1.15,  # 15% profit target
        'max_sell_pct': 0.35  # Sell max 35% of holdings
    },
    'accumulator': {
        'address': os.getenv('WALLET3_ADDRESS'),
        'private_key': os.getenv('WALLET3_PRIVATE_KEY'),
        'min_buy': 0.05,
        'max_buy': 0.15,
        'buy_frequency': 31,  # minutes
        'selling_enabled': False
    },
    'momentum_trader': {
        'address': os.getenv('WALLET4_ADDRESS'),
        'private_key': os.getenv('WALLET4_PRIVATE_KEY'),
        'min_buy': 0.07,
        'max_buy': 0.22,
        'buy_frequency': 43,  # minutes
        'momentum_threshold': 0.03,  # Buy on 3% upward movement
        'selling_enabled': False
    },
    'reserve_wallet': {
        'address': os.getenv('WALLET5_ADDRESS'),
        'private_key': os.getenv('WALLET5_PRIVATE_KEY'),
        'min_buy': 0.25,
        'max_buy': 0.65,
        'buy_frequency': 73,  # minutes
        'only_buy_dips': True,
        'dip_threshold': 0.05,  # Buy on 5% dips
        'selling_enabled': False
    }
}

# Connect to Ethereum
web3 = Web3(Web3.HTTPProvider(os.getenv('ETH_RPC_URL')))
print(f"Connected to Ethereum: {web3.is_connected()}")

# Load ABIs
with open('uniswap_router_abi.json', 'r') as f:
    UNISWAP_ABI = f.read()
    
with open('erc20_abi.json', 'r') as f:
    ERC20_ABI = f.read()

# Contract instances
router_contract = web3.eth.contract(address=UNISWAP_ROUTER, abi=UNISWAP_ABI)
token_contract = web3.eth.contract(address=TOKEN_ADDRESS, abi=ERC20_ABI)

# Historical price tracking
price_history = pd.DataFrame(columns=['timestamp', 'price', 'volume'])

# Get current token price
def get_token_price():
    try:
        # Amount for price check (1 token)
        amount_in = 10**token_contract.functions.decimals().call()
        path = [TOKEN_ADDRESS, WETH_ADDRESS]
        
        # Get amount out
        amounts_out = router_contract.functions.getAmountsOut(
            amount_in,
            path
        ).call()
        
        price_in_eth = amounts_out[1] / amount_in
        return price_in_eth
    except Exception as e:
        print(f"Error getting price: {e}")
        return None

# Execute a buy 
def execute_buy(wallet_name, eth_amount):
    wallet = WALLETS[wallet_name]
    
    # Add randomization to buy amount (±7%)
    variance_pct = random.uniform(-0.07, 0.07)
    adjusted_eth_amount = eth_amount * (1 + variance_pct)
    
    print(f"Executing buy from {wallet_name} for {adjusted_eth_amount:.4f} ETH")
    
    try:
        # Prepare transaction
        nonce = web3.eth.get_transaction_count(wallet['address'])
        deadline = int(time.time() + 300)  # 5 minutes
        
        # Calculate minimum tokens out (5% slippage tolerance)
        path = [WETH_ADDRESS, TOKEN_ADDRESS]
        amounts_out = router_contract.functions.getAmountsOut(
            web3.to_wei(adjusted_eth_amount, 'ether'),
            path
        ).call()
        min_tokens_out = int(amounts_out[1] * 0.95)  # 5% slippage
        
        # Build transaction
        tx = router_contract.functions.swapExactETHForTokens(
            min_tokens_out,
            path,
            wallet['address'],
            deadline
        ).build_transaction({
            'from': wallet['address'],
            'value': web3.to_wei(adjusted_eth_amount, 'ether'),
            'gas': 250000,
            'gasPrice': web3.to_wei('40', 'gwei'),
            'nonce': nonce,
        })
        
        # Sign and send transaction
        signed_tx = web3.eth.account.sign_transaction(tx, private_key=wallet['private_key'])
        tx_hash = web3.eth.send_raw_transaction(signed_tx.rawTransaction)
        
        # Wait for transaction receipt
        receipt = web3.eth.wait_for_transaction_receipt(tx_hash)
        
        print(f"Buy completed: {web3.to_hex(tx_hash)}")
        
        # Log the trade
        log_trade('buy', wallet_name, adjusted_eth_amount, receipt.gasUsed)
        
        return True
    except Exception as e:
        print(f"Error executing buy for {wallet_name}: {e}")
        return False

# Execute a sell
def execute_sell(wallet_name, token_pct):
    wallet = WALLETS[wallet_name]
    
    if not wallet['selling_enabled']:
        return False
    
    try:
        # Get token balance
        token_balance = token_contract.functions.balanceOf(wallet['address']).call()
        
        # Calculate sell amount
        sell_amount = int(token_balance * token_pct)
        
        if sell_amount <= 0:
            print(f"No tokens to sell for {wallet_name}")
            return False
        
        print(f"Executing sell from {wallet_name} for {sell_amount / 10**18:.2f} tokens ({token_pct*100:.1f}%)")
        
        # Approve tokens
        approve_tx = token_contract.functions.approve(
            UNISWAP_ROUTER,
            sell_amount
        ).build_transaction({
            'from': wallet['address'],
            'gas': 100000,
            'gasPrice': web3.to_wei('45', 'gwei'),
            'nonce': web3.eth.get_transaction_count(wallet['address']),
        })
        
        signed_approve = web3.eth.account.sign_transaction(approve_tx, private_key=wallet['private_key'])
        tx_approve_hash = web3.eth.send_raw_transaction(signed_approve.rawTransaction)
        web3.eth.wait_for_transaction_receipt(tx_approve_hash)
        
        # Execute swap
        nonce = web3.eth.get_transaction_count(wallet['address'])
        deadline = int(time.time() + 300)  # 5 minutes
        
        # Calculate minimum ETH out (7% slippage tolerance)
        path = [TOKEN_ADDRESS, WETH_ADDRESS]
        amounts_out = router_contract.functions.getAmountsOut(
            sell_amount,
            path
        ).call()
        min_eth_out = int(amounts_out[1] * 0.93)  # 7% slippage
        
        # Build transaction
        tx = router_contract.functions.swapExactTokensForETH(
            sell_amount,
            min_eth_out,
            path,
            wallet['address'],
            deadline
        ).build_transaction({
            'from': wallet['address'],
            'value': 0,
            'gas': 250000,
            'gasPrice': web3.to_wei('45', 'gwei'),
            'nonce': nonce,
        })
        
        # Sign and send transaction
        signed_tx = web3.eth.account.sign_transaction(tx, private_key=wallet['private_key'])
        tx_hash = web3.eth.send_raw_transaction(signed_tx.rawTransaction)
        
        # Wait for transaction receipt
        receipt = web3.eth.wait_for_transaction_receipt(tx_hash)
        
        print(f"Sell completed: {web3.to_hex(tx_hash)}")
        
        # Log the trade
        log_trade('sell', wallet_name, sell_amount / 10**18, receipt.gasUsed)
        
        return True
    except Exception as e:
        print(f"Error executing sell for {wallet_name}: {e}")
        return False

# Log trades to CSV
def log_trade(trade_type, wallet, amount, gas):
    current_price = get_token_price()
    timestamp = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
    
    with open('trade_log.csv', 'a') as f:
        f.write(f"{timestamp},{trade_type},{wallet},{amount},{current_price},{gas}\n")

# Update price history
def update_price_history():
    global price_history
    
    current_price = get_token_price()
    if current_price is None:
        return
    
    # Get latest 24h volume (approximate)
    # This would require additional logic for accurate volume tracking
    
    new_row = pd.DataFrame([{
        'timestamp': datetime.now(),
        'price': current_price,
        'volume': 0  # Placeholder
    }])
    
    price_history = pd.concat([price_history, new_row], ignore_index=True)
    
    # Keep only last 24 hours of data
    price_history = price_history[price_history['timestamp'] > (datetime.now() - timedelta(hours=24))]
    
    print(f"Current price: {current_price:.10f} ETH")
    
    # Check for price movements
    if len(price_history) > 2:
        last_price = price_history.iloc[-2]['price']
        price_change = (current_price - last_price) / last_price
        print(f"Price change: {price_change*100:.2f}%")
        
        # Check for dips to trigger reserve wallet
        if price_change < -WALLETS['reserve_wallet']['dip_threshold']:
            print("Significant dip detected, triggering reserve wallet buy")
            dip_amount = random.uniform(WALLETS['reserve_wallet']['min_buy'], WALLETS['reserve_wallet']['max_buy'])
            execute_buy('reserve_wallet', dip_amount)
        
        # Check for momentum to trigger momentum trader
        if price_change > WALLETS['momentum_trader']['momentum_threshold']:
            print("Upward momentum detected, triggering momentum trader")
            momentum_amount = random.uniform(WALLETS['momentum_trader']['min_buy'], WALLETS['momentum_trader']['max_buy'])
            execute_buy('momentum_trader', momentum_amount)
        
        # Check sell conditions for swing trader
        if WALLETS['swing_trader']['selling_enabled']:
            # Calculate average purchase price (simplified)
            # In real implementation, this would track actual purchase prices
            avg_buy_price = price_history.iloc[0]['price']
            if current_price > avg_buy_price * WALLETS['swing_trader']['sell_threshold']:
                print("Profit target reached for swing trader, executing partial sell")
                sell_pct = random.uniform(0.15, WALLETS['swing_trader']['max_sell_pct'])
                execute_sell('swing_trader', sell_pct)

# Schedule regular buys for each wallet
def schedule_buys():
    for wallet_name, wallet in WALLETS.items():
        if wallet_name == 'reserve_wallet' or wallet_name == 'momentum_trader':
            # These are triggered by price action, not time
            continue
        
        def create_buy_task(name):
            def task():
                buy_amount = random.uniform(wallet['min_buy'], wallet['max_buy'])
                execute_buy(name, buy_amount)
            return task
        
        # Add randomization to the schedule
        frequency = wallet['buy_frequency']
        jitter = random.randint(-5, 5)  # Add ±5 minutes of randomness
        adjusted_frequency = max(frequency + jitter, 15)  # Minimum 15 minutes
        
        schedule.every(adjusted_frequency).minutes.do(create_buy_task(wallet_name))
        
        # Execute initial buys staggered
        initial_delay = random.randint(1, 15)  # 1-15 minutes initial delay
        print(f"Scheduling initial buy for {wallet_name} in {initial_delay} minutes")
        schedule.every(initial_delay).minutes.do(create_buy_task(wallet_name)).tag('initial')

# Main loop
def main():
    print("Starting trading bot...")
    
    # Schedule price updates
    schedule.every(3).minutes.do(update_price_history)
    
    # Schedule buys
    schedule_buys()
    
    # Run the scheduler
    while True:
        try:
            schedule.run_pending()
            time.sleep(10)  # Check scheduler every 10 seconds
            
            # Remove initial buy tasks after they run
            for job in schedule.get_jobs('initial'):
                if job.last_run is not None:
                    schedule.cancel_job(job)
            
        except Exception as e:
            print(f"Error in main loop: {e}")
            time.sleep(60)  # Wait a minute if there's an error

if __name__ == "__main__":
    # Initial price check
    update_price_history()
    
    # Start the main loop
    main()
```

This trading bot implementation uses sophisticated price action algorithms that simulate realistic trading patterns while maintaining full control over the market movement. The different wallet personas (early investor, swing trader, etc.) create the illusion of diverse market participants while actually being controlled by a single entity.

## 3. Liquidity Pool Monitoring and Extraction Script

This script was used to monitor the liquidity pool size and execute the extraction at the optimal moment.

```javascript
// liquidity-monitor.js - Monitors liquidity pool size and triggers extraction
// Uses ethers.js and custom webhooks for notifications
// Run in parallel with trading bot to determine optimal extraction time

const ethers = require('ethers');
const axios = require('axios');
const fs = require('fs');
const moment = require('moment');
require('dotenv').config();

// Configuration
const TOKEN_ADDRESS = process.env.TOKEN_ADDRESS;
const PAIR_ADDRESS = process.env.PAIR_ADDRESS; // Uniswap V2 pair address
const DISCORD_WEBHOOK = process.env.DISCORD_WEBHOOK;
const TELEGRAM_API_KEY = process.env.TELEGRAM_API_KEY;
const TELEGRAM_CHAT_ID = process.env.TELEGRAM_CHAT_ID;
const PRIVATE_KEY = process.env.EXTRACTION_WALLET_KEY;
const LP_TOKEN_HOLDER = process.env.LP_TOKEN_HOLDER; // Address holding LP tokens

// RPC Endpoints
const PROVIDER_URL = process.env.ETH_RPC_URL;
const provider = new eth
```