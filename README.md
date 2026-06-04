# 🚀 BombSquad Server

A public BombSquad Server with pre-installed mods and mini-games. A VPS is strictly required for 24/7 uptime and global public access.

---

## 📂 Repository Architecture

Here is what each file in this repository does:
*   **`bombsquad_server`**: The core manager script that boots and monitors the server.
*   **`dist/ba_root`**: Contains the core game assets, configurations, and installed mini-games.
*   **`config.yaml` / `config.toml`**: The main configuration files where you control server settings like the party name (**FFA**).

---

## 🛠️ How to Deploy

### 1. Install Dependencies
```bash
sudo apt update && sudo apt install python3.13 python3.13-dev libpython3.13 -y
sudo ln -s $(find /usr -name "libpython3.13.so.1.0" | head -n 1) /usr/lib/libpython3.13.so.1.0
sudo ldconfig
```

### 2. Network & Ports Configuration
You must open **UDP Port 43210** on your Linux instance and your Cloud Provider (AWS Security Groups):
```bash
sudo ufw allow 43210/udp
sudo ufw reload
```

### 3. Launching the Server
Give the server scripts execution rights and run:
```bash
chmod +x bombsquad_server
./bombsquad_server
```
