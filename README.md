# Over protocol node installation
```markdown
# OverProtocol Node Setup

This guide will walk you through setting up a node in the OverProtocol network using various methods, including using OverScape, building from source, or running binaries. You'll also find instructions for setting up validator clients.

## Getting Started

### Prerequisites
- **OS**: 64-bit Linux, Mac OS X 10.14+, Windows 10+
- **CPU**: 4+ cores
- **Memory**: 16GB RAM or more
- **Storage**: SSD with at least 128GB of free space
- **Network**: 25+ MBit/s bandwidth

---

## 1. Running a Node with OverScape

OverScape offers a user-friendly way to set up your node.

### Steps:
1. **Download OverScape**: Get the installer from the [official OverScape website](#) or other trusted sources.
2. **Install the Software**: Follow the on-screen instructions to complete the installation.
3. **Launch and Sync**: Open OverScape, and it will automatically sync with the OverProtocol blockchain.
4. **Node Configuration**: Use the OverScape interface for basic or advanced configuration settings.

---

## 2. Building from Source

For advanced users who prefer to build the node from source.

### Steps:
1. **Clone the Client Repositories**:
   ```bash
   git clone https://github.com/overprotocol/execution-client-kairos.git
   git clone https://github.com/overprotocol/consensus-client-chronos.git
   ```
2. **Install Prerequisites**: Make sure all dependencies are installed (check the repository README for details).
3. **Build the Clients**:
   ```bash
   cd execution-client-kairos
   make build
   cd ../consensus-client-chronos
   make build
   ```
4. **Configure the Node**: Modify the configuration files as needed.
5. **Run the Node**:
   ```bash
   ./kairos --datadir=./data
   ./chronos --datadir=./data
   ```

---

## 3. Running a Node with Binaries

If you prefer pre-compiled binaries, follow these steps.

### Steps:
1. **Create a Directory Structure**:
   ```bash
   mkdir -p ~/overprotocol/{execution,consensus}
   ```
2. **Download Client Binaries**:
   Download the required binaries for your OS:
   - **Execution Client (Kairos)**: 
   - **Consensus Client (Chronos)**:
3. **Run Execution Client**:
   ```bash
   mkdir ~/overprotocol/execution/data
   ./geth --datadir=./execution/data
   ```
4. **Run Consensus Client**:
   ```bash
   mkdir ~/overprotocol/consensus/data
   ./beacon-chain --datadir=./consensus/data --jwt-secret ../execution/data/geth/jwtsecret --checkpoint-sync-url="https://mainnet-checkpoint.over.network"
   ```

---

