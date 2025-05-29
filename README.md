# OverTheWire Bandit Wargame Practice

This repository documents solutions for OverTheWire Bandit Wargame levels 0-9 (currently), focusing on the commands needed to find each level's password. This is part of a larger effort to document 10+ levels daily by me, have documented these as a report / pdf which you can find in the folders

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
