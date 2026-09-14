# Bandit Level 15 → 16

**Challenge:** Retrieve the next password by submitting the current password to port 30001 on localhost — but a plain connection (like the previous level's `nc`) wasn't enough.

**Problem:** The service on this port required an encrypted (SSL/TLS) connection. Plain `nc` or `telnet` can't handle encrypted traffic — they just talk "unencrypted", so the server wouldn't respond correctly.

**Solution:**

ncat --ssl localhost 30001

Then submitted the current password, same as the previous level.

**What I learned:** Some network services require an encrypted connection (SSL/TLS) instead of a plain one. `ncat` supports this with the `--ssl` flag, while plain `nc`/`telnet` cannot handle encrypted traffic at all.
