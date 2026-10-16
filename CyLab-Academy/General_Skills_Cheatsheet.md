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
