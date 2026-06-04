# 🚀 BombSquad FFA Server

BombSquad server manager for v1.7.63.

A public Python-based BombSquad Server Manager with pre-installed mods and mini-games!

---

### ⚠️ Important: Fetch Game Assets
The files in this repository are just the configuration and manager scripts. You need to download the official BombSquad Headless engine files to make it work:

```bash
wget -q "[https://files.ballistica.net/bombsquad/builds/BombSquad_Server_Linux_x86_64_1.7.63.tar.gz](https://files.ballistica.net/bombsquad/builds/BombSquad_Server_Linux_x86_64_1.7.63.tar.gz)" -O server.tar.gz
tar -xzf server.tar.gz --strip-components=1
rm server.tar.gz
```

---

### 📂 Repository Architecture
Here is the breakdown of the files:

*   **`bombsquad_server`**: The core manager script that boots and monitors the server.
*   **`dist/ba_root`**: Contains the core game assets and installed mini-games.
*   **`config.yaml` / `config.toml`**: The main configuration files for server settings (FFA mode).

---

### 🛠️ How to Deploy

**1. Install Dependencies:**
```bash
sudo apt update && sudo apt install software-properties-common -y
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt update
sudo apt install python3.13 python3.13-dev libpython3.13 -y
sudo ln -s $(find /usr -name "libpython3.13.so.1.0" | head -n 1) /usr/lib/libpython3.13.so.1.0
sudo ldconfig
```

**2. Network Ports:**
Open **UDP Port 43210** on your Linux instance:
```bash
sudo ufw allow 43210/udp
sudo ufw reload
```

**3. Run the server:**
```bash
chmod +x bombsquad_server
./bombsquad_server
```

---

### ⚙️ Configuration
Find the `config.yaml` (or `config.toml`) file and open it.
*   Change `party_name` to your desired name (Default: **FFA**).
*   Change `max_party_size` as needed.

**Important Note:** NEVER delete the `.bsac2` or `.bsuuid` files, or your server will lose its identity on the master server.

Need help? Contact on Telegram:
(https://t.me/xo3pe)
