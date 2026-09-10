# Bandit Level 3 → 4

**Challenge:** Password in a hidden file inside the `inhere` directory.

**Problem:** Plain `ls` doesn't show hidden files (names starting with `.`).

**Solution:** `cd inhere` then `ls -la` to reveal the hidden file, then `cat` it.

**What I learned:** Files starting with `.` are hidden by default. `ls -a` (or `-la`) reveals them.
