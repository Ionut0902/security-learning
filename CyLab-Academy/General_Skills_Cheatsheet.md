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




















### 8. Web Exploitation & Source Code Inspection
* **Concept:** Web challenges often hide flags, developer comments, or sensitive logic within the website's front-end source code (HTML, CSS, and JavaScript).
* **Tool:** Browser Developer Tools (accessed via `F12`, `Ctrl+Shift+I`, or Right-Click -> `Inspect`).
* **Notes:** The first step in any web challenge is to thoroughly inspect the page source and all linked asset files. No Linux terminal is required for basic client-side web enumeration.
### 7. Archives & Force Deletion
* **Unzip a file:** `unzip [filename.zip]` (Extracts the contents of a compressed ZIP archive into the current directory).
* **Force Delete Directory:** `rm -rf [directory_name]` (Deletes a folder and all of its nested contents. Standard `rm` or `rmdir` will fail if the folder is not empty. The `-r` means recursive, `-f` means force. Use with caution!).
