# Bandit Level 10 → 11

**Challenge:** Password stored in `data.txt`, encoded in Base64.

**Problem:** The file's content was unreadable text — a Base64-encoded string instead of the actual password.

**Solution:**

base64 -d data.txt

**What I learned:** `base64 -d` decodes a Base64-encoded file back into its original readable content. Base64 is a common way to represent binary or encoded data as plain text.
