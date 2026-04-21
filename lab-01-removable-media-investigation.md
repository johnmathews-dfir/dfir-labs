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
A SHA256 hash was generated from the unmounted device (JM-USB-001) to establish a baseline integrity value.

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
```
The resulting image size matched the original device.

A SHA256 hash of the image matched the original device hash, confirming a successful bit-for-bit forensic copy.

### Analysis and Recovery
The verified image was examined, and files were recovered, including:

- A deleted folder named `Private`
- A deleted XLSX file within that folder
- Multiple image files recovered through carving techniques

## Findings
- Initial acquisition attempts can introduce inconsistencies without careful configuration
- Hash validation is essential for confirming forensic integrity
- Deleted data can be successfully recovered from removable media

## Analysis
The process highlighted the importance of controlled acquisition techniques and validation at each stage.

The mismatch in early attempts demonstrated how small changes in command usage can affect forensic outcomes, reinforcing the need for controlled and repeatable processes.

Successful hash matching confirmed a forensically sound image, suitable for analysis.

## Limitations
- No hardware write blocker was used
- Acquisition was performed in a simulated environment
- Some recovery processes were simplified

## Conclusion
This investigation demonstrated the process of acquiring and validating a forensic image of removable media, as well as recovering deleted artefacts.

It reinforced the importance of evidence integrity, careful methodology and validation through hashing.

## Reflection
This lab provided practical insight into real-world forensic challenges, particularly around acquisition reliability and verification.

It also reinforced the importance of iterative problem-solving and careful validation when handling digital evidence.
