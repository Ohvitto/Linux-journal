# Linux Recap Day - Practice Tasks Summary

## Main Focus

Today was a recap day to practise older Linux topics after taking a break.

The main weak spots to practise were:

- `cd` vs `mv`
- `grep` vs `find`
- `cat` vs `head`
- `>` vs `2>`
- Bash scripts, arguments, permissions, and conditions

---

## Tasks Practised

### 1. Folder Structure

Created a practice area called `LinuxRecap` with folders:

```text
LinuxRecap/
├── Notes/
├── Scripts/
├── Logs/
└── Archive/
```

Commands practised:

```bash
mkdir
mkdir -p
cd
ls
pwd
```

---

### 2. Creating and Writing Files

Created files such as:

```text
Notes/games.txt
Notes/commands.txt
Logs/system.txt
```

Used `echo` with:

```bash
>
>>
```

Example:

```bash
echo "Minecraft" > Notes/games.txt
echo "Roblox" >> Notes/games.txt
```

---

### 3. Searching

Used `find` to locate files:

```bash
find . -name "games.txt"
```

Used `grep` to search inside files:

```bash
grep "Minecraft" Notes/games.txt
grep -i "minecraft" Notes/games.txt
```

Key difference:

```text
find = find files/folders
grep = search inside files
```

---

### 4. Moving and Renaming Files

Used `mv` to rename and move files.

Examples:

```bash
mv Notes/commands.txt Notes/linux_commands.txt
mv Notes/linux_commands.txt Archive/
```

Key difference:

```text
cd = move yourself
mv = move or rename files/folders
```

---

### 5. Viewing Files

Practised viewing files using:

```bash
cat Notes/games.txt
head -n 2 Notes/games.txt
tail -n 2 Notes/games.txt
less Notes/games.txt
```

Inside `less`, practised:

```text
/Minecraft
n
q
```

Meanings:

```text
cat = show whole file
head = show start
tail = show end
less = scroll/search inside file
```

---

### 6. Pipes and Counting

Counted `.txt` files:

```bash
find . -name "*.txt" | wc -l
```

Counted how many times `Minecraft` appeared:

```bash
grep -i "minecraft" Notes/games.txt | wc -l
```

Saved grep history:

```bash
history | grep grep > grep_history.txt
```

---

### 7. Redirection

Saved normal command output:

```bash
df -h > disk_report.txt
```

Saved error output:

```bash
ls fakefolder 2> error_log.txt
```

Key difference:

```text
>  = save normal output
2> = save errors
&> = save normal output and errors
```

---

### 8. Permissions and Scripts

Created a Bash script:

```bash
nano Scripts/hello.sh
```

Used:

```bash
chmod +x Scripts/hello.sh
./Scripts/hello.sh
```

Key concept:

```text
chmod +x = make a script executable
```

---

### 9. Bash Arguments

Created a script using arguments:

```bash
nano Scripts/profile.sh
```

Practised:

```bash
$1
$2
$3
$#
```

Meanings:

```text
$1 = first argument
$2 = second argument
$3 = third argument
$# = number of arguments
```

Example:

```bash
./Scripts/profile.sh Victor 16 Linux
```

---

### 10. Bash Conditions

Created a script that checks whether a file exists:

```bash
if [ -f "$1" ]; then
    echo "$1 is a file"
else
    echo "$1 is not a file"
fi
```

Tested it with:

```bash
./Scripts/check_file.sh Notes/games.txt
./Scripts/check_file.sh fakefile.txt
```

Key concept:

```text
-f = checks if something is a regular file
```

---

## Final Boss Challenge

Created a script called:

```text
Scripts/recap_report.sh
```

The script should print:

1. Username
2. Current folder
3. Date
4. Disk space
5. All `.txt` files
6. Number of `.txt` files
7. Whether `Notes/games.txt` exists

Commands used:

```bash
whoami
pwd
date
df -h
find . -name "*.txt"
find . -name "*.txt" | wc -l
if [ -f "Notes/games.txt" ]; then
```

Saved the report with:

```bash
./Scripts/recap_report.sh > recap_report.txt
cat recap_report.txt
```

---

## Main Thing Learned

Today was a recap day to strengthen old Linux skills and practise combining commands together.

The main focus was understanding when to use:

```text
cd vs mv
grep vs find
cat vs head/tail/less
> vs 2>
chmod +x for scripts
$1, $2, $3, $# for Bash arguments
if [ -f file ] for file checks
```

This recap helped connect many earlier Linux skills into one practical workflow.
