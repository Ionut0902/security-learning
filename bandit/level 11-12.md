# Bandit Level 11 → 12

**Challenge:** Password in `data.txt`, where all letters (a-z, A-Z) have been rotated by 13 positions (ROT13 cipher).

**Problem:** `tr [a-z] [A-Z]` only swaps letter case — it doesn't perform a positional rotation, so it didn't decode the cipher.

**Solution:**

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

**What I learned:** ROT13 shifts each letter 13 positions through the alphabet. `tr` can map one full character range to another — here, the alphabet mapped to itself shifted by 13, decoding the cipher in one step.
