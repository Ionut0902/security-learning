# Bandit Level 2 → 3

**Challenge:** Password in a file named `--spaces in this filename--`.

**Problem:** `cat ./--spaces in this filename--` fails — the shell splits the name into multiple arguments at each space.

**Solution:** Wrapped the filename in quotes: `cat './--spaces in this filename--'`. (Tab-completion also handles this automatically.)

**What I learned:** Spaces separate arguments by default in the shell. Quotes (or backslashes) protect spaces inside a single filename.
