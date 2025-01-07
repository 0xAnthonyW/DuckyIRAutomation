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
DELAY 3000
GUI r
DELAY 500
STRING powershell -Command "Start-Process powershell -ArgumentList '-NoProfile -ExecutionPolicy Bypass -File \"D:\\Test2.ps1\"' -Verb RunAs"
DELAY 500
ENTER
```