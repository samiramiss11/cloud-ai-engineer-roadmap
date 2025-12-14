## DAILY COMMIT STRATEGY ##

# Day 1: added file system practice
# Day 2: permission exercises
# Day 3: process handling notes
# Day 4: Git branching demo
# Day 5: SSH test


## Linux (ADVANCED PRACTICE + EXPLANATION)

## Linux (Advanced Practice & Explanations)

---

### Navigation & File Operations

pwd  
# Print working directory.

ls -lah  
# List all files including hidden, show permissions & sizes.

cd ~/Documents  
# Move to specific directory.

mkdir logs  
# Create directory.

rm file.txt  
# Remove file.
rmdir foldername      or  rm -  foldername
# Remove empty folder   or  non empty folder 

rm -r backups  
# Remove folder recursively.

touch sample.txt  
# Create empty file.

cp config.json backup.json  
# Copy file.

mv draft.txt final.txt  
# Rename or move file.

less server.log  
# View large file page-by-page.

---

### Searching & Filtering

grep "ERROR" app.log  
# Find matching text.

cat app.log | grep -i "fail"  
# Filter case-insensitive.

find . -name "*.log"  
# Recursive file search.

find . -type f -size +10M  
# Large file detection.

---

### Permissions & Ownership

ls -l file.txt  
# Show permissions.

chmod 755 script.sh  
# Set executable access.

chmod 600 secret.env  
# Secure file.

chown user file.txt  
# Change file owner.

---

### Pipes & Redirection

|  
# Pipe output into another command.

echo "error" >> report.txt  
# Append output to file.

cat server.log | grep 500 | wc -l  
# Count HTTP errors.

---

### Process Management

ps aux  
# Show all running processes.

ps aux | grep node  
# Find specific process.

top  
# Resource viewer.

htop  
# Advanced process viewer (if installed).

kill <PID>  
# Graceful termination.

kill -9 <PID>  
# Force kill.

---

### Filesystem & Disk

du -sh *  
# Disk usage by folder.

df -h  
# Disk space info.

tail -f app.log  
# Watch live logs.

---

### Network Diagnostics

ping google.com  
# Test connectivity.

curl https://api.github.com  
# API test.

lsof -i :3000  
# Check open port.

---

### Service Management (Linux only — not macOS)

systemctl status nginx  
# Service status.

systemctl restart docker  
# Restart service.

---

## SSH (Secure Shell Access)

ssh user@server_ip  
# Connect to remote server.

ssh -p 2222 user@server_ip  
# Connect via custom port.

scp file.txt user@server:/home/user  
# Upload file.

scp user@server:/home/user/file.txt .  
# Download file.

ssh-keygen -t ed25519 -C "email@example.com"  
# Generate secure SSH key.

eval "$(ssh-agent -s)"  
# Start SSH agent.

ssh-add ~/.ssh/id_ed25519  
# Add key to agent.

ssh user@server "ls -lh"  
# Run command remotely.

---

### SSH Config Shortcut

~/.ssh/config

Host myserver  
  HostName 1.2.3.4  
  User samira  
  IdentityFile ~/.ssh/id_ed25519  


---



## Git (ADVANCED PRACTICE + EXPLANATION)

### Repository initialization

git init
# Create Git repository.

git status
# Shows changes and file states.

---

### Commit flow

git add .
git commit -m "Meaningful message"
# Never commit unclear messages.

---

### Branching

git branch feature-login
git checkout feature-login
# Create and switch to new branch.

git checkout main
git merge feature-login
# Merge feature into main.

---

### Recovering mistakes

git checkout -- file.txt
# Discard changes.

git reset --soft HEAD~1
# Undo last commit but keep changes.

git reset --hard HEAD~1
# Delete last commit and changes (dangerous).

---

### Viewing history

git log --oneline
# Clean commit history.

git show HEAD
# Inspect last commit.

---

### Remote operations

git push origin main
# Push changes.

git pull origin main
# Pull updates.

---

### Tagging releases

git tag v1.0
git push origin --tags
# Mark versions (like releases).

---

### Debugging conflicts

git diff
# See exactly what changed.

git status
# Shows conflicted files.

---

### Best habits

- Always pull before push
- Never commit secrets
- One feature = one branch



## SSH (ADVANCED PRACTICE + EXPLANATION)

### Generate key

ssh-keygen -t ed25519 -C "email@example.com"
# Secure modern standard algorithm.

---

### Connection

ssh user@host
# Connect to remote machine.

ssh -p 2222 user@host
# Use custom port.

---

### File transfer

scp file.txt user@host:/home/user/
# Upload file.

scp user@host:/home/user/file.txt .
# Download file.

---

### Remote command execution

ssh user@host "ls -lh"
# Run command without opening shell.

---

### SSH Agent

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
# Cache key for session.

---

### Debugging SSH

ssh -v user@host
# Verbose debug mode.

---

### Common SSH problems

Permission denied:
→ Check file permissions.

Connection refused:
→ SSH service not running.

---

### Security practices

- Use SSH keys (not passwords)
- Never share private key
- Use passphrase

---

### Bonus

~/.ssh/config
# Define shortcuts like:

Host myserver
  HostName 1.2.3.4
  User samira
  IdentityFile ~/.ssh/id_ed25519



