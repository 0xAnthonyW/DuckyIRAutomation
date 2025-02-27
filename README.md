# DuckyIRAutomation

This project demonstrates how to use the DSTIKE White Ducky to automate the execution of a PowerShell script with elevated privileges, handle User Account Control (UAC) prompts, and leverage the power of the DuckyScript language.

## Overview

The script utilizes the DSTIKE White Ducky's keyboard emulation capabilities to:
1. Open the Run dialog.
2. Launch PowerShell with elevated privileges.
3. Execute a specified PowerShell script.
4. Automatically accept the UAC prompt.

## Getting Started

### Prerequisites

- DSTIKE White Ducky with  or without IR capabilities.
- A PowerShell script to be executed (e.g., D:\Test2.ps1).
- Basic understanding of DuckyScript syntax.

### Script Details

Below is the DuckyScript used in this project:
```plaintext
REM Open Run dialog and wait for it to appear
DELAY 1000
GUI r
DELAY 1000

REM Type the PowerShell command in segments to avoid issues
STRING powershell -Command "
DELAY 50
STRING Start-Process powershell -ArgumentList '
DELAY 50
STRING -NoProfile -ExecutionPolicy Bypass -File \"
DELAY 50
STRING D:\\slide.ps1\"' -Verb RunAs"
DELAY 100

REM Execute the command
ENTER
DELAY 4000

REM Confirm UAC prompt (Alt+Y = "Yes")
ALT y
```
