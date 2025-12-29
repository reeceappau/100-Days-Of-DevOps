

# Day 4: Grant Executable Permissions to Backup Script

## Task

 xFusionCorp Industries developed an automated backup script (`xfusioncorp.sh`) distributed to all servers, but it lacks executable permissions on App Server 3.
 Grant executable permissions to `/tmp/xfusioncorp.sh` ensuring all users can execute it.

## Solution
```bash
# Grant read and execute permissions to all users
sudo chmod 555 /tmp/xfusioncorp.sh

# Verify permissions
ls -l /tmp/xfusioncorp.sh
```

**Explanation:**
`chmod 555` sets read (r) and execute (x) permissions for owner, group, and others. 

Understanding 555:
- Permission format: `Owner-Group-Others`
- Each digit is a sum: Read(4) + Write(2) + Execute(1)
- `555` = `5-5-5` = `(4+1)-(4+1)-(4+1)` = `r-x r-x r-x`
- All users get read + execute

**Challenge:**
Initially attempted `chmod 111` (execute-only), which failed. Later found that, to execute bash files, the shell interpreter needs both read and execute permission. This is because the shell interpreter must read the script to parse and run it.
