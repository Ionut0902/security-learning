# Bandit Level 13 → 14

**Challenge:** No password given — instead, a private SSH key was provided to log into bandit14 directly.

**Problem:** Running `ssh -i sshkey.private bandit14@localhost -p 2220` from inside the bandit13 session failed — the server blocks connections from localhost to save resources.

**Solution:** Copied the key to the local machine first using `scp`, then connected from there:

scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

**What I learned:** SSH can authenticate with a private key (`-i` flag) instead of a password. `scp` copies files between machines over SSH (note: capital `-P` for port, unlike lowercase `-p` in `ssh`). Some servers block "self-connections" from localhost — read error messages carefully, they often explain exactly what's wrong.
