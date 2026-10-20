# CyLab (picoCTF) - General Skills Cheatsheet

This is a summary of the new commands and concepts I learned while solving the basic challenges on the CyLab platform.

### 1. Remote Connection (SSH)
* **Command:** `ssh -p [port] user@server_address`
* **Example:** `ssh -p 46143 ctf-player@chatelaine.cylabacademy.net`
* **Notes:** I learned how to connect to an external server. For security reasons, the password is not displayed on the screen in Linux while typing.

### 2. Netcat (nc)
* **Command:** `nc [server_address] [port]`
* **Example:** `nc xebec.cylabacademy.net 37881`
* **Notes:** Used to open a simple, raw connection between my computer and a specific port on the server, without requiring a username and password (unlike SSH). 

### 3. Basic Cryptography (ROT13)
* **Command:** `echo "encrypted_text" | tr 'a-zA-Z' 'n-za-mN-ZA-M'`
* **Notes:** ROT13 is a substitution cipher that shifts every letter by 13 positions. I used the `tr` (translate) command directly in the Linux terminal to automatically decode the text, instead of relying on online tools.

### 4. Base64 Decoding
* **Command:** `echo "encoded_text" | base64 -d`
* **Example:** `echo "cGljb0NURnt0ZXN0X2ZsYWd9" | base64 -d`
* **Notes:** Base64 is not a secure encryption algorithm, but merely a data encoding scheme. I used the `-d` (decode) flag directly in the Linux terminal to revert the text back to its original readable format without needing online tools.

### 5. File Management & Executing Binaries
* **Download a file:** `wget [link]` (Downloads a file directly into the Linux terminal).
* **Make executable:** `chmod +x [filename]` (Grants the file permission to be run as a program).
* **Execute & Help Flags:** `./[filename] -h` (Runs a custom executable from the current directory. The `-h` flag opens its help menu, which often contains the CTF flag).
* **Delete a file:** `rm [filename]` (Permanently removes a file to keep the workspace clean).

### 6. Tab Autocompletion & Package Installation
* **Tab Autocompletion:** Pressing the `Tab` key while typing a file or directory name will auto-complete it, preventing typos and saving time. If multiple files share the same prefix, pressing `Tab` twice lists all possible options.
* **Install New Tools:** `sudo apt install [package_name] -y` (Uses the Advanced Package Tool to download and install missing commands, like `unzip`. The `-y` flag automatically answers 'yes' to prompts).

### 7. Archives & Force Deletion
* **Unzip a file:** `unzip [filename.zip]` (Extracts the contents of a compressed ZIP archive into the current directory).
* **Force Delete Directory:** `rm -rf [directory_name]` (Deletes a folder and all of its nested contents. Standard `rm` or `rmdir` will fail if the folder is not empty. The `-r` means recursive, `-f` means force. Use with caution!).

### 8. Web Exploitation & Source Code Inspection
* **Concept:** Web challenges often hide flags, developer comments, or sensitive logic within the website's front-end source code (HTML, CSS, and JavaScript).
* **Tool:** Browser Developer Tools (accessed via `F12`, `Ctrl+Shift+I`, or Right-Click -> `Inspect`).
* **Notes:** The first step in any web challenge is to thoroughly inspect the page source and all linked asset files. No Linux terminal is required for basic client-side web enumeration.

### 9. Binary Analysis & Output Filtering (Piping)
* **Extract Strings:** `strings [filename]` (Extracts and displays only the human-readable text characters from a compiled binary or non-text file).
* **The Pipe Operator:** `|` (Takes the output of the command on the left and passes it as input to the command on the right).
* **Search / Filter:** `grep "keyword"` (Searches through text and outputs only the lines that contain the specified keyword).
* **Combined Example:** `strings challenge_file | grep "CTF"` (Extracts all readable text from a file and instantly filters it to find the flag, saving the effort of reading thousands of lines manually).

### 10. Advanced Search (Only Matching & Regex)
* **Command:** `grep -o "pattern{.*}"`
* **Example:** `cat data.txt | grep -o "academy{.*}"`
* **Notes:** By default, `grep` outputs the entire line where the match was found. If a file consists of one massive continuous line without line breaks, the output will be overwhelming. Using the `-o` (only matching) flag forces `grep` to print strictly the matched phrase. Adding `.*` inside the brackets acts as a wildcard to capture the entire contents of the flag.

### 11. Web Enumeration (robots.txt)
* **Concept:** The `robots.txt` file is a standard plain-text file placed at the root of a website. It instructs search engine crawlers (web robots) which directories or files they are allowed or forbidden to index.
* **Exploitation:** In CTFs, developers often use it to hide sensitive endpoints or flags. By appending `/robots.txt` to the website's main URL, you can publicly view these "hidden" paths.
* **Execution:** Look for lines starting with `Disallow: /[secret_path]` and manually navigate to those endpoints in your browser.

### 13. Script Arguments & Usage Menus
* **Concept:** Many command-line tools and scripts require additional options (arguments) to run correctly. If run without them, they usually print a `Usage:` message indicating the expected syntax.
* **Syntax Breakdown:** In a message like `Usage: script.py (-e/-d) [file]`, the parentheses `()` indicate required choices, and the brackets `[]` indicate placeholders for data (like a filename) where the brackets themselves should not be typed.
* **Example:** `python3 ende.py -d flag.txt.en` (Runs the script, passing `-d` for decrypt and targeting the encrypted file).

### 14. Code Obfuscation & Hexadecimal Values
* **Concept:** Developers (and malware authors) often hide hardcoded passwords or strings by converting them into hexadecimal character codes (e.g., `chr(0x34)` instead of `"4"`).
* **Deobfuscation:** You can quickly decode these strings using Python's interactive shell. 
* **Example:** Open Python by typing `python3`, paste the obfuscated string (e.g., `chr(0x34) + chr(0x61)`), and hit Enter. Python will evaluate the code and print the readable string, revealing the hidden data.

### 15. Script Modification & Brute-Forcing
* **Concept:** Manually entering passwords is not scalable. If a challenge provides a large list of potential passwords (a wordlist), the standard approach is to automate the process (Brute-forcing / Dictionary Attack).
* **Execution:** Instead of running the provided script as-is, edit the source code. Replace the manual user input function (`input()`) with a `for` loop that iterates through every password in an array or a `.txt` file until the correct hash is matched.
* **Mindset:** "Don't work hard, let the computer do the work." Modifying challenge scripts to automate the solution is a core exploitation skill.

### 16. Terminal Text Editing (nano)
* **Concept:** `nano` is a simple, command-line text editor built into Linux. It allows you to view and edit files (like Python scripts) directly within the terminal without needing a graphical interface.
* **Open/Create a file:** `nano [filename.extension]`
* **How to Save and Exit:**
  1. Press `Ctrl + O` (Write Out) to save.
  2. Press `Enter` to confirm the filename.
  3. Press `Ctrl + X` to exit `nano` and return to the terminal shell.

### 17. Hidden Files & Command History
* **Hidden Files:** In Linux, any file or directory that starts with a dot (`.`) is hidden by default. The standard `ls` command will not show them.
* **Viewing Hidden Files:** Use `ls -a` (list all) to reveal hidden files alongside normal ones.
* **History Files:** Files like `.bash_history` or `.python_history` are automatically created by the system to log the commands you type. This is what allows you to press the `Up` arrow key in the terminal to quickly recall and reuse previous commands.

### 18. Python Indentation & Execution Order
* **Indentation Rules:** Python uses whitespace (indentation) instead of curly braces `{}` to define code blocks (`def`, `for`, `if`). Every nested block must be shifted to the right using 1 Tab. Never mix Tabs and Spaces to avoid `IndentationError`.
* **Execution Order:** Python runs scripts sequentially from top to bottom. Variables and functions must be defined in code *before* they are referenced or executed, otherwise Python will throw a `NameError`.

### 19. Reading Wordlists & File Handling in Python
* **Concept:** When potential passwords are stored in an external `.txt` file (a wordlist/dictionary) rather than hardcoded in the script, Python must open and read the file line-by-line to perform a Dictionary Attack.
* **Safe File Opening (`with open`):** Use `with open("dictionary.txt", "r") as f:` to open the file in read mode. The `with` block automatically closes the file after reading, preventing memory leaks.
* **Stripping Newlines (`.strip()`):** Always clean line strings with `.strip()` (e.g., `user_pw = line.strip()`). External `.txt` files store an invisible newline character (`\n`) at the end of every line when you hit Enter. If not stripped, the string hash will include `\n`, causing all password checks to fail.

### 20. Source Code & Element Inspection
* **Concept:** Flags are often embedded directly inside web page source code, HTML comments, hidden tags, or raw text blocks.
* **Execution:** Right-click on the page -> `Inspect` (or `F12` / `Ctrl + U` for View Source) to open Developer Tools.
* **Search Technique:** Use `Ctrl + F` within the source viewer or inspect tab to search for the string `picoCTF{` across all elements, script tags, and comments.


### 21. Advanced Zip Searching & Stream Processing (`unzip -p` & `grep -o`)
* **Stream Archive Content (`unzip -p`):** The `-p` flag outputs the text of all files inside a `.zip` directly to stdout (RAM), allowing you to pipe (`|`) the data directly to `grep` without extracting files to the SSD.
* **Exact Match Extraction (`grep -o`):** The `-o` (*only matching*) flag prints exclusively the text that matches the search pattern (e.g., `picoCTF{...}` or `academy{...}`), discarding all surrounding lines and clutter.
* **One-Liner Flag Extraction:** `unzip -p archive.zip | grep -o "picoCTF{.*}"` extracts and displays the clean flag instantly.
* **Recursive Search on Disk (`grep -r`):** If files are already extracted to disk, use `grep -rn "picoCTF" .` to search recursively through all subdirectories and display file paths with line numbers.

### 23. Reverse Engineering Python Keygens & SHA-256 Indexing
* **Concept:** CTF keygen challenges often reconstruct flags dynamically by hashing user credentials (e.g., `busername`) and comparing specific character indices.
* **Static vs. Dynamic Analysis:** Inspect `check_key()` functions directly using `cat` or `nano` instead of guessing passwords. Identify the hash algorithm (`hashlib.sha256`) and the extracted character index order.
* **Python Reconstruction Script:**
  ```python
  import hashlib
  
  user = b"MORTON"
  h = hashlib.sha256(user).hexdigest()
  
  # Extract dynamic characters based on check_key() index logic
  dynamic_part = h[4] + h[5] + h[3] + h[6] + h[2] + h[7] + h[1] + h[8]
  print(f"picoCTF{{1f_y0u_w4nt_t0_kn0w_{dynamic_part}}}")
