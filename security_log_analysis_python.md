# Security Log Analysis Using Python

## Overview
This project demonstrates how Python can be used by SOC analysts to analyze Windows Security Event Logs and identify suspicious authentication behavior such as repeated failed login attempts that may indicate brute-force attacks.

The project simulates a real-world SOC scenario where automation is used to reduce manual log review and speed up alert triage.

---

## Project Objective
To analyze Windows Security Event Logs using Python and apply basic detection logic to identify abnormal authentication patterns relevant to SOC investigations.

---

## Data Collection
Windows Security Event Logs were generated on a personal test system by performing login and logoff activities.  
These logs were exported from Windows Event Viewer into CSV format for offline analysis using Python.

The exported log data included:
- Event ID
- Timestamp
- Account name
- Logon type

---

## Tools and Technologies Used
- Operating System: Windows  
- Programming Language: Python  
- Log Source: Windows Security Event Logs (CSV format)

### Python Libraries
- csv – used for reading and parsing log files  
- collections – used for counting event occurrences  

---

## Python Script Overview
A Python script was written to parse the exported Windows Security logs and count authentication-related Event IDs.

### Python Code
```python
import csv
from collections import Counter

log_file = "security_logs.csv"
event_counts = Counter()

with open(log_file, newline='', encoding="utf-8", errors="ignore") as file:
    reader = csv.DictReader(file)
    for row in reader:
        event_id = row.get("Event ID")
        if event_id:
            event_counts[event_id] += 1

print("Event ID Analysis:")
for event, count in event_counts.items():
    print(f"Event ID {event}: {count} occurrences")
