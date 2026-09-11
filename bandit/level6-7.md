# Bandit Level 6 → 7

**Challenge:** Password stored somewhere on the server, owned by user bandit7, group bandit6, 33 bytes in size — exact location unknown.

**Problem:** No specific folder given, so local search (`./`) wasn't enough — needed to search the entire filesystem.

**Solution:**

find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

**What I learned:** `find /` searches the whole filesystem from the root, not just the current folder — used when you know a file's properties but not its location. `2>/dev/null` hides "permission denied" errors so only valid results show. `find` can filter by owner (`-user`), group (`-group`), and size (`-size`) at the same time.
