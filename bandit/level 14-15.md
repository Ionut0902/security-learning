# Bandit Level 14 → 15

**Challenge:** Retrieve the next password by submitting the current level's password to port 30000 on localhost.

**Problem:** No file to read this time — the password had to be sent over a network connection instead.

**Solution:**

cat /etc/bandit_pass/bandit14
nc localhost 30000

Then typed the bandit14 password and pressed Enter — the service responded with the bandit15 password.

**What I learned:** `nc` (netcat) opens a direct connection to a network port, letting you send and receive raw data. A port is a numbered channel a service listens on — submitting the right input to it can trigger a response, similar to a simple client-server interaction.
