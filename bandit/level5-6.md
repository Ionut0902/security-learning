# Bandit Level 5 → 6

**Challenge:** Password in a file inside `inhere` with specific properties: 1033 bytes, human-readable.

**First approach:** Used `du -a -b` to check file sizes manually, then navigated with `cd` — worked, but slow and required manual searching through output.

**More efficient way:** `find` searches recursively and filters by criteria in one command:

find inhere -type f -size 1033c

This returns the exact path to the matching file directly, then read it with `cat path/to/file`.

**What I learned:** `find` searches through all subdirectories automatically and can filter by type, size, and other properties — much faster than manually checking with `du` and navigating with `cd`.
