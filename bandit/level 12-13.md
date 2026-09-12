# Bandit Level 12 → 13

**Challenge:** `data.txt` is a hexdump of a file that has been repeatedly compressed/archived through multiple layers (gzip, bzip2, tar, alternating).

**Problem:** Couldn't write in the home directory; needed a safe workspace, plus the file needed to be converted from hexdump back to binary before decompression could even start.

**Solution:**

mktemp -d
cd /tmp/tmp.XXXXXXXXXX
cp ~/data.txt .
xxd -r data.txt > data

Then repeated this cycle for each layer, checking the file type each time and renaming accordingly:

file data
mv data data.<correct_extension>
gzip -d data.<ext>    # or: bzip2 -d data.<ext>   or: tar -xf data.<ext>

Repeated until `file` showed a plain ASCII text file containing the password.

**What I learned:** `xxd -r` converts a hexdump back into its original binary form. Compression/archive layers must be unwrapped one at a time — `mv` renames the file with the correct extension so the decompression tool recognizes it, then `file` reveals what type comes next. `tar` archives (bundles) files rather than compressing them, so it needs `-xf` to extract instead of `-d`.
