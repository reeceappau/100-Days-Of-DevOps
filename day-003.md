# Day 3: Disable Direct SSH Root Login

## Task

 xFusionCorp Industries security team requires disabling direct root SSH access across all app servers in Stratos Datacenter following security audits.

## Solution

bash

```bash
# SSH into each app server
ssh user@app-server

# Edit SSH configuration
sudo vi /etc/ssh/sshd_config

# Change: PermitRootLogin yes → PermitRootLogin no

# Restart SSH service to apply changes
sudo systemctl restart sshd
```

**Challenge Faced:**
Initially did not restart the `sshd` service, which meant configuration changes weren't applied

**Key Learning:** 
Disabling root SSH login prevents attackers from directly brute-forcing the root account. This forces attackers to first authenticate as a regular user before escalating privileges. 
