## Idea
A set of scripts to automatically manage battery charge thresholds based on a weekly schedule. Useful for ensuring a full charge ahead of long mobile sessions while maintaining battery health the rest of the week.

## Installation
1. Copy the script and make it executable:
```bash
sudo cp bat-manager /usr/local/bin/bat-manager
sudo chmod +x /usr/local/bin/bat-manager
```

2. Copy the systemd units:
```bash
sudo cp bat-manager.service /etc/systemd/system/
sudo cp bat-manager.timer /etc/systemd/system/
```

3. Reload and enable:
```bash
sudo systemctl daemon-reload

# Enable the Service (so it hooks into boot/wake)
sudo systemctl enable bat-manager.service

# Enable the Timer (so it handles the specific time triggers)
sudo systemctl enable --now bat-manager.timer
```
