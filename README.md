# Mint CAT20 Tokens on Fractal Network - Step-by-Step Guide

## Prerequisites
- $FB tokens for gas. Get them on [CoinEx](https://www.coinex.com/) or [DotSwap](https://www.dotswap.app/v1/swap#F_FB_BTC).
- A Linux VPS with at least 2 CPU cores and 4GB of RAM. You can rent one here: [vShield](https://vshield.com/).

## Steps

### Step 1: Install the Minting Script

1. Start by logging into your VPS as root to make the process smoother:
   
```
sudo su
```

2. Download and set permissions for the script in one step:

```
wget -O /root/cat20-oooooyoung.sh https://github.com/nopapername/shell-oooooyoung/releases/download/cat20-oooooyoung/cat20-oooooyoung.sh && chmod +x /root/cat20-oooooyoung.sh
```

### Step 2: Run the Script

1. Execute the script to start the process:

```
bash /root/cat20-oooooyoung.sh
```

2. Follow the on-screen instructions. The script provides 5 options:

   1. Install environment dependencies and full node  
   2. Create a wallet  
   3. Start minting CAT20 tokens  
   4. View node sync logs  
   5. Check wallet balance

### Step 3: Wait for Node Sync

1. After selecting **option 1** to install the environment and node, wait for the installation to finish.
2. Once the installation is done, run the script again and choose **option 4** to view the node sync logs.

```
bash /root/cat20-oooooyoung.sh
```

3. Monitor the logs. The node needs to be synced to at least 90% of the current block height. You can verify this by comparing it with the latest block height on [Fractal Explorer](https://explorer.unisat.io/fractal-mainnet/block).

```
LOG [TxService] [OK] mint tx 8541a32b4a5910246c675df88160a72f69361a8d07807544fe4ff97eb0103c85
LOG [TxService] [OK] mint tx d56353772dfaaaed222a62e22c679e58d53a41cff0fc2fa091bd108d89d5f651
LOG [TxService] [OK] mint tx 203df0fafb268f85569d68267ea7bc70d3bc4871967be84b766d53932038d06b
...
```

### Step 4: Create a Wallet

1. After the node is synced, rerun the script and select **option 2** to create a wallet.
2. The script will display the wallet address and mnemonic. Make sure to save the mnemonic somewhere safe.
3. Send a small amount of $FB tokens to the wallet address. If your $FB tokens are on Native Segwit and the script's address is Taproot, manually add the wallet to Unisat using the mnemonic to create a Native Segwit address.

### Step 5: Mint `cat` Tokens

1. Once you have enough $FB in your wallet, rerun the script and select **option 3** to start minting `cat` tokens.
2. The script will ask you to 请输入想要mint的gas (enter the gas fee for minting). Start by trying a gas fee of 300. If that doesn’t work, increase the gas fee incrementally.

That's it! You've successfully minted `cat` tokens on Fractal Network.
