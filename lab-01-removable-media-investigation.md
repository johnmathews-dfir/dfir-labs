# Lab 01: Removable Media Investigation

## Objective
To examine a removable storage device and identify evidence of user activity.

## Scenario
A USB storage device was analysed to determine its contents and potential usage patterns.

## Environment
- Linux Mint
- USB removable drive

## Method

### Device Identification
The device was identified using `lsblk` to confirm its presence and mount point.

### Initial Acquisition Attempt
An attempt was made to create a disk image using `dd` and verify integrity using SHA-256 hashing.

During this process, inconsistencies in hash values were observed, highlighting the challenges of acquisition without specialist hardware such as a write blocker.

### File System Examination
The device was mounted and the directory structure examined.

File metadata, including timestamps, was reviewed to understand activity on the device.

## Findings
- Multiple files were present, including documents and media
- File timestamps showed a sequence of creation and modification
- Activity appeared to occur within a relatively short time window

## Analysis
The observed file activity suggests typical user interaction, including file creation and editing.

The hashing inconsistencies during acquisition demonstrate the importance of controlled forensic processes and proper tooling.

## Limitations
- No write blocker was used
- Imaging process was not forensically sound
- Analysis was conducted on a live system

## Conclusion
This exercise demonstrated how removable media can be examined to identify user activity, while also highlighting the importance of correct acquisition procedures.

## Reflection
This lab provided practical insight into both file system analysis and the challenges of maintaining forensic integrity during evidence handling.
