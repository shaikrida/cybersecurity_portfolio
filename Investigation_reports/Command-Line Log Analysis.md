# Command-Line Log Analysis

## Overview

| Field          | Details                   |
| -------------- | ------------------------- |
| **Scenario**   | Command-Line Log Analysis |
| **Date**       | 1 August 2026             |
| **Analyst**    | Shaik Rida                |
| **Host**       | TCM                       |
| **Log File**   | `access.log`              |
| **Tools Used** | Linux Command Line        |

---

# Commands Used

| Command                          | Description                                                | Screenshot            |
| -------------------------------- | ---------------------------------------------------------- | --------------------- |
| `file access.log`                | Identifies the file type and format              | <img width="554" height="39" alt="image" src="https://github.com/user-attachments/assets/0cbcc0d4-3277-4445-a359-a6345650c7f5" />
 |
| `ls -lh access.log`                | Displays file size and metadata                | <img width="565" height="37" alt="image" src="https://github.com/user-attachments/assets/d568e29c-4608-4389-b89c-33877c070c8e" />
 |
| `wc access.log`               | Counts lines, words, and bytes                    | <img width="536" height="41" alt="image" src="https://github.com/user-attachments/assets/d7e46a25-54d9-4816-8c40-826ef1c98153" />
 |
| `grep "<keyword>" access.log`    | Searches for log entries containing the specified keyword. | *(Insert Screenshot)* |
| `grep -c "<keyword>" access.log` | Counts the number of matching log entries.                 | *(Insert Screenshot)* |
| `sort access.log`                | Sorts the log entries alphabetically.                      | *(Insert Screenshot)* |
| `uniq access.log`                | Displays unique adjacent log entries.                      | *(Insert Screenshot)* |
| `sort access.log \| uniq -c`     | Counts occurrences of unique log entries.                  | *(Insert Screenshot)* |
| `awk '{print $1}' access.log`    | Extracts and displays the first field from each log entry. | *(Insert Screenshot)* |
| `cut -d' ' -f1 access.log`       | Extracts the first space-delimited field.                  | *(Insert Screenshot)* |
| `less access.log`                | Opens the log file for interactive viewing.                | *(Insert Screenshot)* |

---
