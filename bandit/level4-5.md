# Bandit Level 4 → 5

**Challenge:** Password in a file inside a directory with several files, but only one is human-readable.

**Solution:** Checked each file with `cat` to find the readable one. 

**More efficient way:** `file ./*` shows the type of every file at once (e.g., "data" vs "ASCII text") — no need to open each one manually.

**What I learned:** `file` identifies file type without opening it. Wildcards (`*`) let you apply a command to all files in a directory at once — much faster than checking one by one.
