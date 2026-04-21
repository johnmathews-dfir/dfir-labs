# DFIR Lab Structure & Workflow Guide

This document defines the standard structure and workflow for all DFIR labs in this repository.

The goal is consistency, clarity, and reproducibility — not perfection.

---

# 🧠 Core Principles

- Structure is fixed → do not redesign per lab
- Logs are factual → not polished
- Notes are messy → thinking space
- Findings are clean → communication
- Commands are reusable → not a transcript

---

# 📁 Standard Lab Naming

Use:

DFIR-XXX-Short-Description

Examples:
- DFIR-001-USB-Acquisition
- DFIR-002-Deleted-File-Recovery
- DFIR-003-Timeline-Analysis

Do NOT include dates in lab names.

---

# 📁 Standard Folder Structure

Each lab follows this structure:

---

DFIR-XXX-Name/
│
├── 00_admin/
│ ├── 00_forensic_log.md
│ ├── 01_notes.md
│ ├── 02_commands.md
│ └── case_info.md (optional)
│
├── 01_acquisition/
│ ├── images/
│ ├── hashes/
│ └── logs/
│
├── 02_analysis/
│ ├── recovered_files/
│ ├── logs/ (optional)
│ └── analysis_notes.md (optional)
│
├── 03_report/
│ ├── 03_findings.md
│ └── 04_summary.md
│
└── screenshots/ (optional)


---

# 🧠 What Goes Where

## 🟢 00_admin/00_forensic_log.md
Purpose: Chain of events (forensic audit trail)

Contains:
- timestamps
- actions taken
- commands used
- results (brief)
- factual notes

Format:

[YYYY-MM-DD HH:MM] Action
Command:
Result:
Notes:

Rule:
Write what happened, not what it means.

---

## 🟡 00_admin/01_notes.md
Purpose: Thinking space

Contains:
- ideas
- hypotheses
- confusion
- next steps

Rule:
Messy is allowed.

---

## 💻 00_admin/02_commands.md
Purpose: Clean, reusable commands

Contains:
- final working commands only
- no commentary
- no failed attempts

Rule:
If you’d reuse it → it goes here

---

## 📂 01_acquisition/

### images/
- forensic images (.img)
- versioned (v1, v2, final)

### hashes/
- SHA256 files
- device + image hashes

### logs/
- raw tool outputs
- terminal captures
- command outputs

Rule:
Logs = evidence, not curated

---

## 📂 02_analysis/

### recovered_files/
- carved or recovered artefacts

### logs/ (optional)
- Sleuth Kit / carving outputs

### analysis_notes.md (optional)
- structured thinking during analysis

---

## 📄 03_report/03_findings.md
Purpose: Clear output of investigation

Structure:

Summary:
What was done

Key Findings:

bullet points

Issues Encountered:

problems or limitations

Conclusion:
What this demonstrates

Rule:
Clear > clever

---

## 📄 03_report/04_summary.md
Purpose: Portfolio / interview summary

Contains:
- short explanation of lab
- key learning points
- significance

Rule:
This should be readable in under 30 seconds

---

# 🔁 Workflow (Follow Every Time)

1. Perform actions
2. Log key steps in forensic log
3. Dump thoughts in notes
4. Save outputs in logs/
5. At the end:
   - update commands.md
   - write findings.md
   - optionally write summary.md

---

# 🧠 Logs vs Commands (Critical Distinction)

Commands.md:
- clean
- reusable
- final versions only

logs/:
- raw output
- messy
- full record

Rule:
Commands = what worked
Logs = what happened

---

# 🕒 Timestamps & Naming

Use timestamps in:
- forensic_log.md
- log filenames (optional)

Format:
YYYY-MM-DD HH:MM

Optional file naming:
example_20260419.log

Do NOT add dates to:
- lab names
- folder structure

---

# ⚠️ Anti-Refactor Rule

Do NOT:
- redesign structure mid-lab
- move files between layers unnecessarily
- merge notes, logs, and findings

If something feels messy:
→ leave it
→ fix structure in the next lab

Consistency > perfection

---

# 🎯 Purpose of This System

This structure demonstrates:

- methodical thinking
- evidential integrity
- repeatable workflow
- clear communication

These are more important than tool complexity.

---

# ✅ Final Reminder

You are not documenting everything.

You are demonstrating:

- how you think
- how you work
- how you validate evidence

Stick to the structure.
Trust the process.
Move forward.

