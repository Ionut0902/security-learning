# Bandit Level 1 → 2

**Challenge:** Password in a file literally named `-`.

**Problem:** `cat -` doesn't work — `-` has special meaning (reads from keyboard input).

**Solution:** `cat ./-` — forces `-` to be treated as a filename.

**What I learned:** Some characters (like `-`) have special meaning to commands. Prefixing with `./` forces them to be treated as literal filenames.
