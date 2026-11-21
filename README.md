# NETWORKWALKS--THABO-MTSHISELWA-B084-WK3-PM1-AND-PM2-PASSWORD-CRACKING-WITH-JTR-AND-NW-TOOLS
Password Cracking/decrypting encrypted files
# Password Cracking with JTR & NetworkWalks Tools

**Cybersecurity & Ethical Hacking Project — Week 3**

This repository documents two project modules focused on password cracking
against password-protected PDF files:

| Module | Title | Tools Used |
|--------|-------|------------|
| W3-PM1 | Password Cracking with JTR | John the Ripper (Jumbo), Johnny GUI, OnlineHashCrack |
| W3-PM2 | Password Cracking with NW Tools | NetworkWalks Hash Calculator & Password Cracker |

## Repository Contents

- [`W3-PM1_JTR/`](./W3-PM1_JTR/) John the Ripper / Johnny GUI walkthrough
- [`W3-PM2_NW-Tools/`](./W3-PM2_NW-Tools/) — NetworkWalks web-tool walkthrough
- [`flags/`](./flags/flags) — Captured flags from both modules

## Disclaimer

All activities were performed in an authorized lab environment for
educational purposes only. Never crack passwords on systems you do not own
or have explicit permission to test.

# W3-PM1: Password Cracking with JTR

**Objective:** Learn to crack passwords using John the Ripper (JTR),
Johnny GUI (front-end), and OnlineHashCrack, then decrypt a
password-protected PDF.

## Tools & Downloads

| Tool | Source |
|------|--------|
| John the Ripper 1.9.0-Jumbo | https://www.openwall.com/john/ |
| Johnny GUI 2.2 (CURRENT) | https://openwall.info/wiki/john/johnny |
| PDF Hash Extractor | https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php |

> **Note:** Johnny GUI is the **front end**; John the Ripper is the **back end**.

---

## Step 1 — Download John the Ripper

Download **1.9.0-Jumbo** from the official Openwall site, choosing the build
for your OS (Windows, Linux, macOS, etc.).

<img width="602" height="270" alt="JTR Download page" src="https://github.com/user-attachments/assets/93305d2d-4ba6-41c6-9010-6402cbc59ff0" />

---

## Step 2 — Download Johnny GUI

Download **Binaries 2.2 (CURRENT)** from the official Johnny wiki, matching
your OS.

<img width="602" height="290" alt="Johnny GUI Download 1" src="https://github.com/user-attachments/assets/2cd09ebd-b630-4ee3-b241-d14c7dc696e4" />
<img width="602" height="288" alt="Johnny GUI Download 2" src="https://github.com/user-attachments/assets/1d1046e4-24d6-4ded-b393-949abc42d7da" />

---

## Step 3 — Install Johnny GUI & Configure JTR Path

1. Extract the downloaded zip files.
2. Run the Johnny installer.

<img width="502" height="413" alt="Johnny GUI Installation" src="https://github.com/user-attachments/assets/b8ab04ee-87e1-40c9-bd29-318dafd50bdf" />

3. Open Johnny GUI → **Settings** → **Browse**.
4. Select your John the Ripper folder and choose `john.exe` (Windows) as the
   executable path. Click **Run**.

<img width="752" height="400" alt="Configuring john exe path" src="https://github.com/user-attachments/assets/15f1433c-2bb2-49ab-a80d-6baebf0d2c8b" />

---

## Step 4 — Extract the PDF Hash

1. Open https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php
2. Upload the encrypted PDF (`My Locked PDF1.pdf`).
3. Copy the extracted hash — it begins with `$pdf$...`.

<img width="602" height="299" alt="Uploading PDF to hash extractor" src="https://github.com/user-attachments/assets/53a0ae1c-9359-4250-b60e-17194dc129d1" />

4. Paste the hash into a new text file (e.g. `Hash Value1.txt`) and save it.

<img width="752" height="386" alt="Saving hash to text file" src="https://github.com/user-attachments/assets/e379df9a-1b4b-4d13-8e11-15c6ea15c4a7" />

---

## Step 5 — Run the Attack in Johnny

1. In Johnny GUI, click **Open password file**.
2. Browse to `Hash Value1.txt` and click **Open**.
3. Click **Start attack**.

<img width="752" height="399" alt="Opening password file in Johnny" src="https://github.com/user-attachments/assets/17d381be-dbde-4e72-8070-b6157f857cbe" />

Cracking may take some time depending on CPU speed and password complexity.

---

## Step 6 — Retrieve the Cracked Password

When the attack completes, the plaintext password appears in the **Password**
column (in this run: `good-luck`).

<img width="752" height="395" alt="Cracked password shown in Johnny" src="https://github.com/user-attachments/assets/cf555769-eb52-40ad-8bfe-3e962f765668" />

---

## Step 7 — Decrypt the PDF

1. Open the encrypted PDF.
2. Enter the recovered password at the prompt.

<img width="752" height="395" alt="PDF password prompt" src="https://github.com/user-attachments/assets/b9789e39-9efe-4fc1-ae1b-1e39ed96b771" />

3. The PDF unlocks successfully — congratulations screen with the flag.

<img width="602" height="320" alt="Decrypted PDF — Flag 1" src="https://github.com/user-attachments/assets/8b4a1eef-efb1-4320-9ed0-41ab0419b907" />

**Flag 1:** `nw{cybersecurity_flag_captured_2606}`

<img width="602" height="320" alt="Decrypted PDF — Flag 1" src="https://github.com/user-attachments/assets/341c496a-4cc4-4ee4-a68e-31c790758dce" />

# W3-PM2: Password Cracking with NetworkWalks Tools

**Objective:** Use NetworkWalks' online Hash Calculator and Password Cracker
(dictionary attack) to recover a PDF password and decrypt a second
protected PDF.

## Tools

| Tool | URL |
|------|-----|
| Hash Calculator | https://networkwalks.com/hash-calculator/ |
| Password Cracker | https://networkwalks.com/password-cracker/ |

---

## Step 1 — Extract the PDF Hash

1. Open the NetworkWalks Hash Calculator.
2. Upload / drag-and-drop the locked PDF (`My Locked PDF2.pdf`).
3. The tool parses the file locally and returns a crackable hash starting
   with `$pdf$` (pdf2john / hashcat-compatible format).

<img width="602" height="303" alt="NW Hash Calculator" src="https://github.com/user-attachments/assets/0b627b54-e39d-4db0-91f2-1d3ef03aec86" />

---

## Step 2 — Open the Password Cracker

Copy the **complete** `$pdf$...` hash (do not omit any part) and open:

https://networkwalks.com/password-cracker/

<img width="602" height="304" alt="NW Password Cracker page" src="https://github.com/user-attachments/assets/ae5434d8-523f-4dcd-9598-ae774a446213" />

---

## Step 3 — Run the Dictionary Attack

1. Paste the `$pdf$` hash into the input field.
2. Keep the built-in list (100 passwords) selected, or upload your own
   wordlist (`.txt`).
3. Click **START CRACKING**.

<img width="602" height="303" alt="Starting the crack" src="https://github.com/user-attachments/assets/4729c5c8-0448-4659-b4c6-df72507f7580" />

The tool hashes each candidate word and compares it against the PDF hash,
logging attempts until a match is found.

---

## Step 4 — Retrieve Password & Decrypt the PDF

The tool displays **PASSWORD CRACKED SUCCESSFULLY** with the plaintext
password (in this run: `password1`).

<img width="602" height="303" alt="Password found" src="https://github.com/user-attachments/assets/888b4070-1140-4912-b490-fde2b17f3a69" />

Open the PDF and enter the recovered password — the document unlocks and
reveals the second flag.

<img width="602" height="320" alt="Decrypted PDF — Flag 2" src="https://github.com/user-attachments/assets/00e6695b-c1e5-41fc-ab5f-6b45563cbc00" />

**Flag 2:** `nw{cybersecurity_flag_captured_2025}`

# Captured Flags

| Module | Flag |
|--------|------|
| W3-PM1 (JTR / Johnny GUI) | `nw{cybersecurity_flag_captured_2606}` |
| W3-PM2 (NetworkWalks Tools) | `nw{cybersecurity_flag_captured_2025}` |

# Conclusion: 6 Key Learnings from the Password Cracking Project

## 6 Key Learnings
## 1. Johnny GUI is a front end — John the Ripper is the actual engine
Johnny provides a convenient interface, but it cannot crack anything on its own. The user must configure the path to (john.exe) under **Settings** → **Browse** before any attack can run. Understanding this front-end/back-end relationship is essential for setup and troubleshooting.

## 2. PDF passwords are stored as crackable hashes, not plaintext
Tools such as OnlineHashCrack's PDF Hash Extractor and NetworkWalks' Hash Calculator convert an encrypted PDF into a ($pdf$...) hash (pdf2john / hashcat-compatible format). Cracking means recovering the password from that hash — the PDF itself is only decrypted once the correct password is found.

## 3. Hash extraction must be complete and exact
Every character of the ($pdf$) hash matters. Truncating or missing part of the hash when saving it to a text file will cause the cracker to fail silently or produce no match. The full string must be copied from ($pdf$) to the end.

## 4. Cracking speed depends on password complexity and hardware
Johnny/JTR attacks may take considerable time depending on CPU speed and password complexity. In the NetworkWalks dictionary attack, the tool tested 100 candidate passwords and found (password1) after 91 attempts — showing that weak passwords fall quickly, while strong passwords demand larger wordlists or brute-force masks.

## 5. Dictionary attacks are highly effective against weak passwords
The NetworkWalks Password Cracker hashes every word in a wordlist and compares it against the PDF hash — the same principle behind the well-known "rockyou" list. This demonstrates why reusing common passwords (e.g., (password1), (good-luck)) is dangerous, and why strong, unique passphrases are essential.

## 6. The workflow is repeatable across different tools
Both modules follow the same logical pipeline:

Extract hash → Feed to cracker → Recover password → Unlock file

Whether using Johnny GUI with JTR or a browser-based NetworkWalks tool, the underlying method is identical. Password cracking is a systematic process, not magic — and defenders must assume attackers have these tools readily available.

**Author**: Thabo Mtshiselwa

**Program**: Cybersecurity program at Networkwalks | Week: 03 | Cybersecurity Professional B084

**Date**: 21 November 2026


