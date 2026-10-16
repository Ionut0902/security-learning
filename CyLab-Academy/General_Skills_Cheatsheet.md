# CyLab (picoCTF) - General Skills Cheatsheet

Acesta este un rezumat al comenzilor și conceptelor noi pe care le-am învățat rezolvând provocările de bază de pe platforma CyLab.

### 1. Conectare la distanță (SSH)
* **Comanda:** `ssh -p [port] user@adresa_server`
* **Exemplu:** `ssh -p 46143 ctf-player@chatelaine.cylabacademy.net`
* **Note:** Am învățat cum să mă conectez la un server extern. Din motive de securitate, în Linux parola nu se afișează pe ecran în timp ce o tastezi.

### 2. Netcat (nc)
* **Comanda:** `nc [adresa_server] [port]`
* **Exemplu:** `nc xebec.cylabacademy.net 37881`
* **Note:** Este folosit pentru a deschide o conexiune directă și brută între calculatorul meu și un anumit port de pe server, fără a necesita utilizator și parolă (cum face SSH-ul). 

### 3. Criptografia de bază (ROT13)
* **Comanda:** `echo "text_criptat" | tr 'a-zA-Z' 'n-za-mN-ZA-M'`
* **Note:** ROT13 este un algoritm de substituție care mută fiecare literă cu 13 poziții. Am folosit comanda `tr` (translate) direct în terminalul de Linux pentru a decoda automat textul, în loc să folosesc unelte online.
