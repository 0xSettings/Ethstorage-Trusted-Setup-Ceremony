# EthStorage V1 Trusted Setup Ceremony

![EthStorage V1 Trusted Setup Ceremony](../Ethstorage-Trusted-Setup-Ceremony/img/ethstorage.png)

## Introduction
This guide explains how to take part in the **EthStorage V1 Trusted Setup Ceremony**, which generates secure parameters for our **Groth16 zk-SNARK circuits** — a core part of EthStorage’s proof-of-storage system.

EthStorage is a **Layer 2 network** that enables fully on-chain data storage for games, social platforms, AI, and more.  
The ceremony ensures our network remains **secure, tamper-proof, and decentralized**.

**Event Duration:** August 13 – 22, 2025

---

## Participation Requirements

### Supported Platforms
You can join using:
- Linux
- macOS
- Windows with WSL (Linux subsystem)
- VPS running Ubuntu

### GitHub Account Criteria
Your GitHub account must:
- Be at least **30 days old**
- Have **1 or more public repositories**
- Follow **at least 5 other accounts** and have **at least 1 follower**
- Allow read/write access to **GitHub Gists** for the ceremony tool

### Internet Connection
Maintain a **stable and continuous** connection — the queue can last several hours.

---

## Step 1: Install System Dependencies

**Update & Upgrade Packages**
```bash
sudo apt-get update && sudo apt-get upgrade -y
```


1. Install Required Tools
```bash
sudo apt install curl screen iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev ca-certificates -y
```

## Step 2: Install NVM & Node.js 18

Install NVM
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source .bashrc
```


## Install Node.js 18
```bash
nvm install 18
nvm use 18
source ~/.bashrc
```
Step 3: Install and Authenticate Ceremony CLI

## Create Working Directory
```bash
mkdir ~/trusted-setup-tmp && cd ~/trusted-setup-tmp
```

## Install CLI Tool
```bash 
npm install -g @p0tion/phase2cli
```

## Authenticate with GitHub
```bash 
phase2cli auth
```
Visit: https://github.com/login/device
Enter the code from your terminal
Authorize ethstorage to proceed

Step 4: Join the Ceremony

## (VPS Users) Start a Screen Session
```bash 
screen -S ceremony
```

## Run Contribution Command
```bash 
phase2cli contribute -c ethstorage-v1-trusted-setup-ceremony
```

Press Enter to use a random seed
Or type any combination of letters/numbers manually
Useful Screen Commands
Detach session: Ctrl + A + D

Reattach session:
```bash
screen -r ceremony
```


End ceremony (inside screen): Ctrl + C
Exit screen: Ctrl + D
Kill session from outside:

screen -XS ceremony quit


## List sessions:
```bash 
screen -ls
```
## Notes
Queue wait times vary — patience is required
If interrupted, re-run the same command to resume
After finishing, you’ll get an option to share your contribution on social media 🎉

Step 5: Cleanup & Logout

## Remove local files and revoke GitHub access
```bash 
phase2cli clean
phase2cli logout
rm -rf ~/trusted-setup-tmp
```

