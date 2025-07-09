# Windows Event Log Analysis (Lab)

This project demonstrates how to use Windows Event Viewer and Sysmon to detect suspicious system activity — specifically, PowerShell command execution using obfuscation. All logs shown were generated locally for educational purposes.

---

## 🛠Tools Used
- **Windows Event Viewer**
- **Sysmon** (System Monitor) by Sysinternals
- **Command Prompt / PowerShell**
- **GitHub** for documentation

---

## Steps Performed

### Step 1: Basic Event Log Exploration
- Used Windows Event Viewer to analyze:
  - **4625**: Failed Logon
  - **4672**: Special Privileges Assigned
  - **4688**: Process Creation
  - **4720**: User Account Creation

### Step 2: Install Sysmon
- Installed Sysmon with a basic config to track process creation
- Verified Event ID **1 (Process Create)** was being captured

### Step 3: Simulate Suspicious Activity
- Ran an **obfuscated PowerShell command** using `-EncodedCommand`
- Captured the encoded PowerShell execution in **Sysmon Event ID 1**

---

## Screenshots
Screenshots included (with sensitive data blurred) showing:
- Sysmon configuration
- Encoded PowerShell command in cmd
- Corresponding Sysmon log (Event ID 1)

---

## Real-World Relevance

This simulation represents a common early-stage attack pattern:
> An attacker uses a Base64-encoded PowerShell payload to evade detection and execute malicious commands.

SOC analysts often use Sysmon + a SIEM (like Splunk or Sentinel) to detect and alert on this behavior.

---

## What I Learned

- How to set up and configure Sysmon
- How encoded PowerShell appears in logs
- How attackers attempt to evade defenses
- How to document and analyze event logs clearly

