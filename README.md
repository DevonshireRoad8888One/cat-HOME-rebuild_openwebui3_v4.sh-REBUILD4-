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
cd ~/openwebui3
./check-security.sh

Security Features (All Enabled)Open WebUI and Ollama bound to localhost only (127.0.0.1)
Authentication required
New user signups disabled
CORS restricted to localhost
Ollama origins restricted
Secret key stored in protected .webui_secret_key (600 permissions)
.env file locked down (600 permissions)
Data, models, logs, and run folders locked down (700 permissions)

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

