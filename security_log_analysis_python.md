# Security Log Analysis Using Python

## Project Objective
To analyze Windows Security Event Logs using Python in order to detect suspicious authentication activity such as repeated failed login attempts that may indicate brute-force attacks.

---

## Background
SOC analysts frequently deal with large volumes of authentication logs. Manual review of these logs is time-consuming and error-prone. Automating log analysis using Python helps identify suspicious patterns quickly and improves investigation efficiency.

This project demonstrates a simple Python-based approach to analyzing Windows Security logs in a SOC-style workflow.

---

## Data Collection
Windows Security Event Logs were generated on a personal system by performing login and logoff activities. These logs were exported from Event Viewer into CSV format for offline analysis.

The log file contained the following fields:
- Event ID
- Timestamp
- Account Name
- Logon Type

---

## Tools and Technologies
- **Operating System:** Windows  
- **Programming Language:** Python  
- **Log Format:** CSV (exported Windows Security logs)

### Python Libraries Used
- `csv` – for reading and parsing log files  
- `collections` – for counting event occurrences  

---

## Python Script Overview
A Python script named `log_analyzer.py` was created to parse the exported security logs and count authentication-related events.

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