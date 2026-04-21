# Lab 01: Removable Media Forensic Acquisition and Analysis

## Objective
To simulate the forensic acquisition and analysis of a removable storage device, ensuring evidence integrity and recovering user data.

## Scenario
A USB storage device (JM-USB-001) was obtained for examination. The objective was to create a forensic image and analyse its contents while maintaining evidential integrity.

## Environment
- Linux Mint
- Removable USB storage device

## Method

### Initial Integrity Check
A SHA256 hash was generated from the unmounted device to establish a baseline integrity value.

### First Acquisition Attempt
A forensic image was created using `dd`.  
A SHA256 hash of the resulting image did not match the original device hash, indicating an issue with the acquisition process.

### Validation and Reattempt
A second hash of the original device confirmed no changes had occurred, ruling out modification of the source media.

A second imaging attempt revealed a size mismatch between the device and the image, suggesting potential padding or acquisition inconsistencies.

### Successful Acquisition
A third imaging attempt was performed using a simplified `dd` command:

```bash
sudo dd if=/dev/sdb of=JM-USB-001-3.img bs=4M status=progress
