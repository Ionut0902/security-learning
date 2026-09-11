# Bandit Level 9 → 10

**Challenge:** `data.txt` is a binary file. The password is on a line preceded by several `=` characters, but the exact number wasn't specified ("several").

**Problem:** The file isn't plain text, so it can't be read directly with `cat`. Also didn't know exactly how many `=` characters to search for.

**Solution:** Used `strings` to extract readable text from the binary file, then filtered with `grep` starting with a broad guess (`==`) to see the results:

strings data.txt | grep "=="

**What I learned:** `strings` pulls readable text out of binary/non-text files. When unsure of an exact pattern (like how many repeated characters), start with a broad search and narrow it down based on how many results come back.
