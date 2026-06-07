# cat-HOME-rebuild_openwebui3_v4.sh-REBUILD4-
cat > "$HOME/rebuild_openwebui3_v4.sh" &lt;&lt;'REBUILD4'

README - Secure Open WebUI v4 (Fixed & Hardened)Fully self-contained local installer — No more CORS semicolon bugs.How to Install / ReinstallPaste the entire installer script (the big cat > "$HOME/rebuild_openwebui3_v4.sh" block) into your Ubuntu terminal.
Press Enter a couple of times.
Run this command:

bash

chmod +x ~/rebuild_openwebui3_v4.sh && ~/rebuild_openwebui3_v4.sh

The script will:Install everything fresh
Apply all security fixes
Start Open WebUI automatically

First Time SetupAfter the installer finishes:Open your browser and go to:
http://127.0.0.1:8001
Create your admin account (this is the only signup allowed).

Done! Useful Commands (after installation)bash

# Start Open WebUI + Ollama
cd ~/openwebui3
./start.sh

# Stop everything cleanly
cd ~/openwebui3
./stop.sh

# Check security status
cd ~/openwebui3 && ./check-security.sh

Security Features (All Enabled)Open WebUI and Ollama bound to localhost only (127.0.0.1)
Authentication required
New user signups disabled
CORS restricted to localhost
Ollama origins restricted
Secret key stored in protected .webui_secret_key (600 permissions)
.env file locked down (600 permissions)
Data, models, logs, and run folders locked down (700 permissions)

 Perfect! Your security check passed cleanly.Everything looks excellent: Both Open WebUI and Ollama are bound to localhost only (127.0.0.1)
 Correct strict permissions on folders and files
 Both services are running and responding properly

Your setup is now properly hardened.

Folder Structure

~/openwebui3/
├── start.sh              ← Start server
├── stop.sh               ← Stop server
├── check-security.sh     ← Security audit
├── .env                  ← Settings (do not edit manually)
├── .webui_secret_key     ← Protected secret key
├── env1/                 ← Python virtual environment
├── data/                 ← Database & settings
├── models/               ← Downloaded Ollama models
├── logs/                 ← Log files
└── run/                  ← PID files

To Update LaterJust run the installer script again:bash

~/rebuild_openwebui3_v4.sh

It will rebuild everything cleanly with the latest fixes.You now have a clean, stable, and secure local Open WebUI setup.  

Maintenance Guide & Quick CommandsOne-Command Quick Start (Recommended)After installation, you can start everything with just one command:bash

cd ~/openwebui3 && ./start.sh

Bookmark this — you’ll use it most often.Full Maintenance Guide1. Daily Usebash

# Start
cd ~/openwebui3 && ./start.sh

# Stop
cd ~/openwebui3 && ./stop.sh

# Check security & status
cd ~/openwebui3 && ./check-security.sh

2. Update Open WebUI to Newer Versionbash

cd ~/openwebui3

# Stop first
./stop.sh

# Re-run the installer (it will update Open WebUI)
~/rebuild_openwebui3_v4.sh

You can change the version inside the rebuild_openwebui3_v4.sh script by editing this line:
OPENWEBUI_VERSION="0.9.6"
3. Backup Your Setup (Recommended before big updates)bash

cd ~
tar -czf openwebui3_backup_$(date +%Y-%m-%d).tar.gz openwebui3
echo "✅ Backup created: ~/openwebui3_backup_$(date +%Y-%m-%d).tar.gz"

To restore:bash

cd ~
tar -xzf openwebui3_backup_YYYY-MM-DD.tar.gz

4. Full Reinstall / Reset Everythingbash

~/rebuild_openwebui3_v4.sh

This wipes the old folder and installs fresh (your models will stay if you want — just don’t delete the models/ folder).5. Change Port (Optional)Edit the installer script and change:bash

WEBUI_PORT="8001"
OLLAMA_PORT="11436"

Then re-run the installer.6. View Logs (if something goes wrong)bash

cd ~/openwebui3
tail -n 100 logs/ollama.log
# or
tail -f logs/ollama.log     # live view

One-Command Quick Reference Card (Copy-Paste Version)bash

# === QUICK COMMANDS ===
cd ~/openwebui3
./start.sh              # Start
./stop.sh               # Stop
./check-security.sh     # Security check

# Update / Reinstall
~/rebuild_openwebui3_v4.sh

# Backup
cd ~ && tar -czf openwebui3_backup_$(date +%Y-%m-%d).tar.gz openwebui3

Secure Open WebUI v4 - Local Hardened SetupFully Fixed & Self-Contained InstallerThis is a secure, localhost-only installation of Open WebUI with Ollama.Installation / ReinstallationCopy and paste the entire installer script (cat > "$HOME/rebuild_openwebui3_v4.sh" ...) into your terminal.
Press Enter.
Run this one command:

bash

chmod +x ~/rebuild_openwebui3_v4.sh && ~/rebuild_openwebui3_v4.sh

The script will install everything and start the server automatically.First LaunchAfter installation finishes:Open your browser and go to:
http://127.0.0.1:8001
Create your admin account (this is the only signup allowed).

Quick CommandsAction
Command
Start Open WebUI + Ollama
cd ~/openwebui3 && ./start.sh
Stop everything
cd ~/openwebui3 && ./stop.sh
Check security & status
cd ~/openwebui3 && ./check-security.sh
Reinstall / Update
~/rebuild_openwebui3_v4.sh
Create Backup
cd ~ && tar -czf openwebui3_backup_$(date +%Y-%m-%d).tar.gz openwebui3

Security Features (All Enabled)Bound to localhost only (127.0.0.1)
Authentication required
New user signups disabled
CORS restricted to localhost
Ollama origins restricted
Secret key stored in protected file (permissions 600)
.env file locked (600)
Data, models, logs, and run folders locked (700)

Folder Structure

~/openwebui3/
├── start.sh                 # Start server
├── stop.sh                  # Stop server
├── check-security.sh        # Security & status check
├── .env                     # Settings (do not edit manually)
├── .webui_secret_key        # Protected secret key
├── env1/                    # Python virtual environment
├── data/                    # Database and user data
├── models/                  # Ollama models (safe to keep)
├── logs/                    # Log files
└── run/                     # PID files

Maintenance GuideUpdate Open WebUI  bash

~/rebuild_openwebui3_v4.sh

Backup (recommended before updates)  bash

cd ~ && tar -czf openwebui3_backup_$(date +%Y-%m-%d).tar.gz openwebui3

Restore Backup  bash

cd ~ && tar -xzf openwebui3_backup_YYYY-MM-DD.tar.gz

View Logs  bash

cd ~/openwebui3
tail -n 100 logs/ollama.log

Change Version
Edit OPENWEBUI_VERSION="0.9.6" inside ~/rebuild_openwebui3_v4.sh, then re-run the installer.Important NotesThis setup is designed for local use only (laptop/desktop).
Do not forward ports 8001 or 11436 unless you add extra protection (reverse proxy + HTTPS).
Web search / external tools in Open WebUI can still make outbound internet requests.

You’re all set!
Your Open WebUI is now running securely and cleanly.How to Save This READMERun this command to create the file:bash

cat > ~/openwebui3/README.md << 'EOM'
[ Paste the entire README content above here ]
EOM

Would you like me to also create a short desktop shortcut / alias or an update script for even easier maintenance?

