# Common Commands
These are a list of some common, useful linux commands used in basic CTF challenges. I've compiled them mostly from playing Bandit - OverTheWire puzzles.

## man
Displays the manual/help page for any command.

### Common Flags
- -k: Search for a keyword across all man pages (man -k ls)
- -f: Shows a brief desc of command (man -f ls)

### Example
`man grep`


## du
Shows disk usage of files and directories.

### Common Flags
- -h: Human readable sizes (du -h)
- -sh: Show summary only (du -sh myfolder)
- -max-depth=1: Limit subdirectory levels (du -h -max-depth=1)

### Tips
- Can be used to find which files are the largest or taking up the most space.
- Can be used with sort to sort the files in terms of size.


## find
Searches for files and directories recursively (goes into directories).

### Commonn Flags
- -name: Matches files with the name (find . -name "myname.txt")
- -type f: Matches only files, no folders (find . -type f)
- -group: Matches group (find / -group grpname)
- -user: Matches file with specified user (find / -user username)
- -size: Matches files with specified size (find . -size 33c)
- -size +-: Matches files greater/less than specified size (find . -size +10MB)

### Tips
- All files and folders have users and can have groups. They can be seen by running ls -l.
- Very useful to find files in large directories as it searches recursively downwards.
- Can refer to cheatsheets to see other flags and variations.


## grep
Search for lines that match a pattern in the files or output. By output, it means we can use pipelines to search the output of another command. For example, we could search for a user by running ls -l to get all the info and searching the username.

### Common Flags
- -r: Recursively search into directories (grep -r "flag" myfolder)
- -i: Ignore case (grep -i "flag" file.txt)
- -n: Show line numbers (grep -n "flag" file.txt)
- -v: Invert match, shows all lines without the match (grep -v "flag" file.txt)
- -a: Treats binary files like text (grep -a "flag" binaryfile)

### Tips
- Can be used to search for flags in CTFs.


## sort
Sorts lines in a file alphabetically by default.

### Common Flags
- -n: Sort numerically (sort -n scores.txt)
- -r: Reverse order (sort -n reverse.txt)
- -u: Uniques only, remove duplicates (sort -u names.txt) (equivalent to sort names.txt | uniq)

### Tips
- Can be used with other commands to sort by columns or other specifications.


## uniq
Removes **adjacent** duplicates lines from input.

### Common Flags
- -c: Counts how many times a line appears (sort lines.txt | uniq -c)

### Tips
- Must sort before using or it won't work. Only identifies adjacent duplicates.


## strings
Strings a binary or unknown file and extracts any printable ASCII text. Does this by analyzing the bit sequences.

### Common Flags
- -n: Sets minimum string length. *Default is 4 chars*. (strings -n 3 file.bn)

### Tips
- Can be used to find hidden flags in files.
- Can help detect embedded passwords.
- View metadata in images (captions basically).









































