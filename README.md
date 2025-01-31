# Hidden Process ID Finder

## Overview

This Python script analyzes process information from two input files (`pslist` and `psxview`) to identify hidden or suspicious processes. It compares the Process IDs (PIDs) from both files and outputs any PIDs present in `psxview` but missing in `pslist`. This can be useful for detecting potential rootkits or hidden processes in memory forensics.

---

## Features

### Key Functionality
1. **Extract PIDs**: Extracts Process IDs (PIDs) from specified columns in the `pslist` and `psxview` files.
2. **Compare Processes**: Compares the PIDs from both files to identify discrepancies.
3. **Hidden Process Detection**: Outputs PIDs that are present in `psxview` but not in `pslist`, indicating potentially hidden processes.

---

## Requirements

### Prerequisites
- Python 3.x
- Required Python libraries:
  - `sys`

### Installation
No additional dependencies are required. Simply clone this repository and run the script.

```bash
git clone https://github.com/THeZoNE-007/hidden-pid-finder.git
cd hidden-pid-finder
```

---

## Usage

### Running the Script
1. Prepare your `pslist` and `psxview` files. These files should contain process information with PIDs in specific columns.
   - `pslist`: PID is expected in the first column (index 0).
   - `psxview`: PID is expected in the third column (index 2).

2. Run the script using the following command:
   ```bash
   python hiddenPID.py <path_to_pslist_file> <path_to_psxview_file>
   ```
   Example:
   ```bash
   python hiddenPID.py pslist_output.txt psxview_output.txt
   ```

3. The script will output any hidden PIDs directly to the console.

---

## Example Output

If hidden processes are detected:
```
PID: 1234
PID: 5678
```

If no hidden processes are found:
```
No PIDs found in psxview that are not present in pslist.
```

---

## Acknowledgments

- Inspired by memory forensics techniques for detecting hidden processes.
- Designed for use with tools like Volatility that generate `pslist` and `psxview` outputs.
