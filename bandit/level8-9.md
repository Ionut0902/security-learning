# Bandit Level 8 → 9

**Challenge:** Password is the only line in `data.txt` that appears exactly once (all other lines are duplicated).

**Problem:** `uniq` alone only removes duplicate lines that are next to each other — in an unsorted file, duplicates can be scattered anywhere.

**Solution:**

sort data.txt | uniq -u

`sort` orders all lines alphabetically so duplicates end up adjacent, then `uniq -u` shows only the lines that appear exactly once.

**What I learned:** The pipe (`|`) connects commands — the output of the first becomes the input of the second, without needing an intermediate file. This is different from `;`, which just runs commands separately with no connection between them.
