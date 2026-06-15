
# Security Log Analysis Using Python

## Overview
This project demonstrates how Python can be used to analyze Windows Security Event Logs to detect suspicious authentication activity such as repeated failed login attempts.

It simulates how SOC analysts automate log analysis tasks to quickly identify potential brute-force attacks and abnormal login behavior.

---

## Project Objective
To analyze Windows Security Event Logs using Python and apply basic detection logic to identify suspicious authentication patterns.

---

## Skills Demonstrated
- Python scripting for security analysis  
- Windows authentication log analysis  
- CSV log parsing and processing  
- Event correlation and counting  
- Brute-force detection logic  
- SOC-style investigation workflow  

---

## Tools & Technologies Used
- **Programming Language:** Python  
- **Operating System:** Windows  
- **Log Source:** Windows Security Event Logs (CSV format)

---

## Key Windows Event IDs
- **4624** – Successful logon  
- **4625** – Failed logon  
- **4634** – Logoff  

---

## Investigation Summary
Windows Security logs were exported to CSV format and analyzed using a Python script. The script counted authentication-related events and highlighted abnormal patterns such as multiple failed login attempts within a short period.

This approach helps SOC analysts quickly triage authentication alerts and prioritize investigations.

---

## SOC Outcome
Suspicious authentication behavior can be efficiently identified and escalated for further investigation using simple Python automation.

---

