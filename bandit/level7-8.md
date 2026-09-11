# Bandit Level 7 → 8

**Challenge:** Password stored in `data.txt`, on the line containing the word "millionth".

**Problem:** File was large — needed to search for a specific word instead of reading the whole thing.

**Solution:**

grep millionth data.txt

**What I learned:** `grep word filename` searches a file and prints only the lines containing that word. Quotes around the search word or filename are only needed if they contain spaces — a single word doesn't need them.
