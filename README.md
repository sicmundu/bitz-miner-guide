# 🚀 bitz Node Manager - Your Ultimate bitz Miner Companion! 🚀

Welcome to the **bitz Node Manager**, a powerful and user-friendly script brought to you by the **xnod3 project**! This tool simplifies the setup, management, and maintenance of your bitz Miner node on Debian-based Linux systems (like Ubuntu).

Run it directly with a one-liner – no download needed!

## ✨ Features

*   🚀 **Easy Installation**: Get your bitz Miner node up and running in minutes.
*   💼 **Wallet Management**: Guides you through Solana wallet creation and funding.
*   ⚙️ **Service Control**: Seamlessly manage your node with systemd service integration (start, stop, restart, status).
*   🔄 **Simple Updates**: Keep your bitz Miner updated with a single command.
*   📜 **Log Viewing**: Easily access your node's logs.
*   🗑️ **Clean Removal**: Uninstall the node and its dependencies cleanly.
*   🎨 **User-Friendly Interface**: Colorful output with emojis for a better experience.
*   🛡️ **Error Handling**: Built-in checks to guide you through potential issues.

## 📋 Prerequisites

*   A **Debian-based Linux system** (e.g., Ubuntu 20.04 LTS or newer).
*   **`sudo` (administrator) privileges**.
*   A stable **internet connection**.
*   **`curl`** installed (usually available by default on most Linux systems).

## ⚡ One-Liner Execution

No need to download the script first! You can run any command directly from your terminal using `curl`:

```bash
bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) <command>
```

Replace `<command>` with one of the available commands listed below.

## 🛠️ Available Commands

Here's what you can do with the bitz Node Manager:

*   `install`         - 🚀 Installs and configures the bitz Miner node.
*   `remove`          - 🗑️ Removes the bitz Miner node and its components.
*   `update`          - 🔄 Updates the bitz Miner software.
*   `logs`            - 📜 Shows the live logs for the bitz Miner service.
*   `service-status`  - ⚙️ Displays the current status of the bitz Miner service.
*   `start-service`   - ▶️ Starts the bitz Miner service.
*   `stop-service`    - ⏹️ Stops the bitz Miner service.
*   `restart-service` - 🔄 Restarts the bitz Miner service.
*   `help`            - ❓ Shows the help message with all available commands.

## 🚀 Step-by-Step Installation Guide

To install your bitz Miner node, open your terminal and run:

```bash
sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) install
```

**Follow the on-screen prompts carefully. Key steps include:**

1.  **System Setup**: The script will update your system and install necessary dependencies (like Rust, Solana CLI, etc.).
2.  **💼 Solana Wallet Creation**:
    *   You will be guided to create a new Solana wallet.
    *   **❗ CRITICAL ❗**: When your **mnemonic phrase** (a series of words) is displayed, **SAVE IT SECURELY AND OFFLINE**. This is the ONLY way to recover your wallet. Losing it means losing access to your funds.
    *   The script will save the keypair to `~/.config/solana/id.json` for operational use, but the mnemonic is your ultimate backup.
3.  **🙏 Wallet Funding**:
    *   The script will display your new Solana wallet's public address (e.g., `YourWalletAddressXXXXXXXXXXXXXXX`).
    *   You will be prompted to fund this wallet with a small amount of **ETH** (e.g., 0.001 ETH) to cover initial transaction fees for the bitz network operations.
        ```
        ℹ️ INFO Please fund your new Solana wallet: YourWalletAddressXXXXXXXXXXXXXXX
           You will need a small amount of ETH (e.g., 0.001 ETH) to cover transaction fees.
           The script will automatically continue once funds are detected in the wallet.
        Press Enter when you are ready to start checking the balance...
        ```
    *   The script will then wait and periodically check your wallet balance. Once sufficient funds (enough to be greater than a very small SOL threshold, as the balance check itself is on Solana) are detected, the installation will proceed automatically.
4.  **bitz Miner Installation**: The `bitz` software will be installed.
5.  **Systemd Service Setup**: A service named `bitz-miner.service` will be created, enabled, and started. This ensures your node runs automatically, even after a reboot.

Once completed, your bitz Miner node will be up and running! ✅

## ⚙️ Managing Your Node

Always use `sudo` when running commands that manage the service or perform system-level changes.

*   **Check Node Status**:
    ```bash
    sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) service-status
    ```
*   **View Node Logs**:
    ```bash
    sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) logs
    ```
    (Press `Ctrl+C` to stop viewing logs.)

*   **Stop the Node Service**:
    ```bash
    sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) stop-service
    ```
*   **Start the Node Service** (if previously stopped):
    ```bash
    sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) start-service
    ```
*   **Restart the Node Service**:
    ```bash
    sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) restart-service
    ```

## 🔄 Updating the Node

To update your bitz Miner software to the latest version:

```bash
sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) update
```
This will stop the service (if running with sudo), update `bitz`, and restart the service.

## 🗑️ Removing the Node

If you need to remove the bitz Miner node:

```bash
sudo bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) remove
```
This will:
*   Stop and disable the `bitz-miner` service.
*   Remove the service file.
*   Uninstall `bitz`.
*   Optionally prompt you to remove Solana CLI and Rust.

## ❓ Getting Help

To see the list of all commands and usage instructions directly from the script:

```bash
bash <(curl -s https://scripts.xnod3.com/nodes/bitz_manager.sh) help
```

---

Enjoy managing your bitz Miner node with ease!

**Made with ❤️ by the xnod3 project.** 
