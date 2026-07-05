┌─────────────────────────────────────────────────────────────┐
│ ⚡ Full Installation Commands ─ TERMUX & KALI LINUX ⚡ │
│ Instagram Brute Forcer Ultimate Edition │
└──────────────────────────────────────────────────────────┘
📱 TERMUX Commands (Android)
1. Update core packages and install prerequisites:
bash
pkg update -y && pkg upgrade -y
pkg install python -y
pkg install python-pip -y
pkg install openssl -y
pkg install tor -y
pkg install curl -y
pkg install git -y
pkg install wget -y
pkg install root-repo -y
pkg install x11-repo -y
2. Install the required Python libraries:
bash
pip install --upgrade
pip install requests
pip install requests[socks]
pip install PySocks
pip install urllib3
pip install stem
pip install cryptography
pip install python-telegram-bot
pip install colorama
pip install aiohttp
pip install aiohttp[socks]
3. Set up Tor in Termux:
bash
# Create a Tor data folder
mkdir -p $PREFIX/var/lib/tor
mkdir -p $PREFIX/etc/tor
# Write Tor settings
cat > $PREFIX/etc/tor/torrc << EOF
SocksPort 9050
ControlPort 9051
DataDirectory $PREFIX/var/lib/tor
Log notice syslog
EOF

# Run Tor
tor &
4. Load and run the tool:
bash
# Load the script
wget https://raw.githubusercontent.com/HA-MRX/InstaBrute/main/insta.py -O insta.py

# Or create the file manually
nano insta.py
# (Paste the full code here, then Ctrl+X, then Y, then Enter)

# Run the tool
python insta.py
5. Quick run command (everything at once):
bash
pkg update -y && pkg upgrade -y && pkg install python python-pip openssl tor curl git wget -y && pip install requests PySocks urllib3 stem cryptography python-telegram-bot colorama && tor & && sleep 3 && python insta.py
=============================================================================================================================================================================================================================
💻 Kali Linux Commands
1. System Update and Installation Requirements:
bash
sudo apt update -y && sudo apt upgrade -y
sudo apt install python3 -y
sudo apt install python3-pip -y
sudo apt install openssl -y
sudo apt install tor -y
sudo apt install curl -y
sudo apt install git -y
sudo apt install wget -y
sudo apt install build-essential -y
sudo apt install libssl-dev -y
sudo apt install libffi-dev -y
sudo apt install python3-dev -y
2. Python Libraries Installation:
bash
pip3 install --upgrade pip
pip3 install requests
pip3 install requests[socks]
pip3 install PySocks
pip3 install urllib3
pip3 install stem
pip3 install cryptography
pip3 install python-telegram-bot
pip3 install colorama
pip3 install aiohttp
pip3 install aiohttp[socks]
pip3 install beautifulsoup4
pip3 install lxml
3. Setting up and running Tor:
bash
# Start the Tor service
sudo systemctl start tor
sudo systemctl enable tor

# Or manually
sudo tor &

# Verify that Tor is working
curl --socks5 localhost:9050 https://check.torproject.org

# Change Tor settings (optional)
sudo nano /etc/tor/torrc
# Add these lines:
# SocksPort 9050
# ControlPort 9051
# Then:
sudo systemctl restart tor
4. Download and run Tool:

bash
# Create a folder for the tool
mkdir -p ~/instabrute
cd ~/instabrute

# Load the script
wget https://raw.githubusercontent.com/HA-MRX/InstaBrute/main/insta.py -O insta.py

# Or create it manually
nano insta.py
# (Paste the code then Ctrl+X then Y then Enter)

# Grant execution permissions
chmod +x insta.py

# Run the tool
sudo python3 insta.py
5. Quick Run Command (Everything at once):
bash
sudo apt update -y && sudo apt install python3 python3-pip tor curl openssl -y && sudo systemctl start tor && pip3 install requests PySocks urllib3 stem cryptography python-telegram-bot colorama && cd ~ && wget -O insta.py https://raw.githubusercontent.com/HA-MRX/InstaBrute/main/insta.py && sudo python3 insta.py
🔧 Troubleshooting Common Issues
Tor Issues in Termux:
bash
# If Tor is not working
pkill tor
rm -rf $PREFIX/var/lib/tor/*
tor --DataDirectory $PREFIX/var/lib/tor --SocksPort 9050 &
Pip Issues in Termux:
bash
# If installing some libraries fails
pip install --no-cache-dir <library_name>
# Or
MATHLIB=m pip install <library_name>
Permissions Issues in Kali:
bash
# Run without sudo if problems occur
python3 insta.py --no-root

# Or create a default Tor user
sudo usermod -a -G debian-tor $USER
Check Ports:
bash
# Verify that Tor is working on port 9050
netstat -tlnp | grep 9050
ss -tlnp | grep 9050
📦 Requirements File (requirements.txt)
Create a requirements.txt file with the following content:

text
requests>=2.28.0
PySocks>=1.7.1
urllib3>=1.26.0
stem>=1.8.0
cryptography>=38.0.0
python-telegram-bot>=13.0
colorama>=0.4.6
aiohttp>=3.8.0
Then install it with the command:

bash
pip install -r requirements.txt
🚀 Very Fast Run
Termux (One Copy & Paste):
bash
pkg update -y && pkg upgrade -y && pkg install python python-pip openssl tor curl -y && pip install requests PySocks urllib3 stem cryptography python-telegram-bot colorama && tor --SocksPort 9050 --ControlPort 9051 &disown && sleep 3 && python3 -c "$(curl -fsSL https://pastebin.com/raw/XXXXX)"
Kali Linux (copy and paste one):
bash
sudo apt update -y && sudo apt install python3 python3-pip tor openssl curl -y && sudo systemctl start tor && pip3 install requests PySocks urllib3 stem cryptography python-telegram-bot colorama && sudo python3 <(curl -fsSL https://pastebin.com/raw/XXXXX)
⚠️ Important Notes
Make sure you have an internet connection before installing.

In Termux, some operations require a VPN if Tor is blocked.
