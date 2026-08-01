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
| `file access.log`                | Identifies the file type and format of `access.log`.       | <img width="641" height="48" alt="image" src="https://github.com/user-attachments/assets/cc6bdbf1-c694-414d-89ab-a252c00863f7" />
 |
| `head access.log`                | Displays the first 10 lines of the log file.               | *(Insert Screenshot)* |
| `tail access.log`                | Displays the last 10 lines of the log file.                | *(Insert Screenshot)* |
| `wc -l access.log`               | Counts the total number of log entries.                    | *(Insert Screenshot)* |
| `grep "<keyword>" access.log`    | Searches for log entries containing the specified keyword. | *(Insert Screenshot)* |
| `grep -c "<keyword>" access.log` | Counts the number of matching log entries.                 | *(Insert Screenshot)* |
| `sort access.log`                | Sorts the log entries alphabetically.                      | *(Insert Screenshot)* |
| `uniq access.log`                | Displays unique adjacent log entries.                      | *(Insert Screenshot)* |
| `sort access.log \| uniq -c`     | Counts occurrences of unique log entries.                  | *(Insert Screenshot)* |
| `awk '{print $1}' access.log`    | Extracts and displays the first field from each log entry. | *(Insert Screenshot)* |
| `cut -d' ' -f1 access.log`       | Extracts the first space-delimited field.                  | *(Insert Screenshot)* |
| `less access.log`                | Opens the log file for interactive viewing.                | *(Insert Screenshot)* |

---
