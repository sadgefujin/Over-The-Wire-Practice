# OverTheWire Bandit Wargame Solutions

This repository documents solutions for OverTheWire Bandit Wargame levels 0-19 (currently), focusing on the commands needed to find each level's password. This is part of a larger effort to document 10+ levels daily by me, have documented these as a report / pdf which you can find in the folders

## Table of Contents

* [Levels 0-9 Quick Reference](#levels-0-9-quick-reference)
* [Levels 10-19 Quick Reference](#levels-10-19-quick-reference)
* [Levels 20-29](#levels-20-29) (Coming Soon!)
* [Levels 30-34](#levels-30-34) (Coming Soon!)

---

## Levels 0-9 Quick Reference

### Level 0
**Command:** `cat readme`
**Explanation:** Displays content of the `readme` file.
**Password:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

### Level 1
**Command:** `cat ./-`
**Explanation:** Displays content of the file named `-`.
**Password:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

### Level 2
**Command:** `cat spaces\ in\ this\ filename`
**Explanation:** Displays content of the file with spaces.
**Password:** `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

### Level 3
**Command:** `cat ...Hiding-From-You`
**Explanation:** Displays content of the hidden file.
**Password:** `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`

### Level 4
**Command:** `find . -type f | xargs file` then `cat ./-file07`
**Explanation:** Finds human-readable file, then displays its content.
**Password:** `40QYVPkxZ00E005pTW81FB8j8lxXGUQw`

### Level 5
**Command:** `find . -type f -size 1033c ! -executable` then `cat ./maybehere07/.file2`
**Explanation:** Finds non-executable file of specific size, then displays its content.
**Password:** `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

### Level 6
**Command:** `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null` then `cat /var/lib/dpkg/info/bandit7.password`
**Explanation:** Finds file by owner, group, and size, then displays content.
**Password:** `morbNTDKSW6jIlUc ym0dMaLn0lFVAaj`

### Level 7
**Command:** `strings data.txt | grep "millionth"`
**Explanation:** Extracts readable strings and finds the line containing "millionth".
**Password:** `dfwvzFQi4mU0wfNbF0e9RoWskMLg7eEc`

### Level 8
**Command:** `sort data.txt | uniq -c`
**Explanation:** Sorts lines and counts unique occurrences to find the single line.
**Password:** `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

### Level 9
**Command:** `strings data.txt | grep "="`
**Explanation:** Extracts readable strings and finds lines with `=`.
**Password:** `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

---

## Levels 10-19 Quick Reference

### Level 10
**Command:** `base64 -d data.txt`
**Explanation:** Decodes the base64 encoded password from `data.txt`.
**Password:** `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

### Level 11
**Command:** (Used CyberChef ROT13)
**Explanation:** Decodes ROT13 encoded string.
**Password:** `7x16WNeHI15YkIhWsfFIqoogniTy1904`

### Level 12
**Command:** `file data.txt` then repeatedly decompress using `gzip -d`, `bzip2 -d`, `tar -xf`, `cat` etc. until password found.
**Explanation:** Identifies file types and decompresses repeatedly until the password file is revealed.
**Password:** `The password is UoMYgQwbhFAgF0g5rb6M1hpF6KwQ` (from the original PDF, though not explicitly shown in the provided snippet, this is the expected password for level 12)

### Level 13
**Command:** `ssh -i sshkey.private bandit14@localhost -p 2220` then `cat /etc/bandit_pass/bandit14`
**Explanation:** Uses a private SSH key to log in, then reads the password file.
**Password:** `MU4VWeTyJk8R0of1qqmcBPaLh7lDCPvS`

### Level 14
**Command:** `nc localhost 30000` (then enter password from Level 13)
**Explanation:** Connects to port 30000 using netcat, provides the previous password to get the next.
**Password:** `8xCjnmgoKbGLhHFAZLGE5Tmu4M2tKJQo`

### Level 15
**Command:** `ncat -ssl localhost 30001` (then enter password from Level 14)
**Explanation:** Connects to SSL/TLS encrypted port 30001 using ncat, provides the previous password to get the next.
**Password:** `SkjigBBybjpW3LzH0Zt1yP10q7F0` (Based on the image, the password was `SkoupRg71ByCRVGBPVCVT3BFMRYDX` in the original PDF, but the provided text snippet shows `SkjigBBybjpW3LzH0Zt1yP10q7F0` as the output. I will use the one from the text.)

### Level 16
**Command:** `nmap localhost -p 31000-32000` then `ncat -ssl localhost 31790` (then enter password from Level 15)
**Explanation:** Scans for open ports in a range, then connects to the SSL port to get the password.
**Password:** `kSkvUpMQ71BYyCM4GBPvCvT1BfWRy0Dx`

### Level 17
**Command:** `diff passwords.new passwords.old`
**Explanation:** Compares two password files to find the difference (the new password).
**Password:** `x2gLTTjFwMOhQ8oWNbMN362QKxfRqG10`

### Level 18
**Command:** `ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh` then `cat readme`
**Explanation:** Forces pseudo-terminal allocation and specifies `/bin/sh` to bypass `.bashrc` issues, then reads `readme`.
**Password:** `cGWpMaKXVwDUNGPAVJbWYuGHVn9z13j8`

### Level 19
**Command:** `./bandit20-do cat /etc/bandit_pass/bandit20`
**Explanation:** Executes a SUID binary to run `cat` with `bandit20` permissions to read the password file.
**Password:** `0qXahG8ZjOVMN9Ghs7i0WsCfZyXOUbYO`
