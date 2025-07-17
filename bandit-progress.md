# OverTheWire: Bandit Lab Notes

## Level 0 → 1
- Command used: `cat readme`
- Learned: How to read a basic file in the terminal.

## Level 1 → 2
- Problem: File was named `-`, which confused the shell.
- Solution: Used `cat ./-` to treat it as a file, not an option.
- Learned: Special characters like `-` need special handling.

## Level 2 → 3
- Problem: File had spaces in its name.
- Solution: Used `cat "spaces in this filename"`
- Learned: Use quotes or backslashes for filenames with spaces.

## Level 3 → 4
- Problem: Hidden file with a tricky name.
- Solution: Used `ls -la` to find hidden files. Then used `cat "... hiding-from-you"`
- Learned: Hidden files start with `.` and can have special names that require quotes or escaping.

## Level 4 → 5

**Challenge**: Find a human-readable file **in the inhere directory** with **1033 bytes**, **not executable**, and **owned by bandit6:bandit5**.

**Learned Commands**:
- `find`: Locate files by attributes (size, owner, permissions)
- `xargs`: Pass output from one command as arguments to another (used for reading file contents)

**Commands Used**:
```bash
find . -type f -size 1033c ! -executable -user bandit6 -group bandit5 | xargs cat
