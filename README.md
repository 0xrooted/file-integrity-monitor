# File Integrity Monitor (FIM)

This project is a simple **File Integrity Monitoring tool** written in Python.

It watches a folder and detects if any file is:

- Added
- Modified
- Deleted

It works by creating a **baseline** of file hashes and then comparing the current state of files with that baseline.

This type of tool is commonly used in **Cybersecurity, DFIR, and SOC environments** to detect unauthorized changes in important files.

---

## How it works

1. The program scans all files inside a monitored directory.
2. It calculates the SHA256 hash of each file.
3. On the first run, it creates a **baseline** and saves it.
4. On the next runs, it compares current hashes with the baseline.
5. It reports:
   - New files
   - Modified files
   - Deleted files
6. A report is generated automatically.

---

## Project Structure

```
file-integrity-monitor/
│
├── data/               # Stores baseline.json
├── monitored_dir/      # Folder being monitored
├── reports/            # Generated reports
├── src/
│   ├── integrity.py    # Hash calculation
│   ├── baseline.py     # Baseline creation and loading
│   ├── scanner.py      # Directory scanning
│   ├── reporter.py     # Report generation
│   └── main.py         # Main execution
```

---

## Requirements

- Python 3.x
- No external libraries required

---

## How to Run

### Step 1 — First run (create baseline)

```bash
python src/main.py
```

This will create a baseline of current files.

---

### Step 2 — Make some changes

- Add a new file in `monitored_dir`
- Modify an existing file
- Delete a file

---

### Step 3 — Run again

```bash
python src/main.py
```

You will see the comparison report in the terminal and inside the `reports` folder.

---

## What this project demonstrates

- Working with file handling in Python
- Hashing and integrity checking
- Practical understanding of how FIM tools work
- Basic DFIR/SOC relevant concept implementation

---

## Use Case in Real World

File Integrity Monitoring is used in:

- SOC monitoring
- DFIR investigations
- Detecting malware persistence
- Detecting unauthorized system changes

This project is a basic implementation of the same concept.