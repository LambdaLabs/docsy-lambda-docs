---
title: "How do I gather system information in Windows using DxDiag?"
type: docs
tags:
- troubleshooting
---

You can use the
[DirectX Diagnostic Tool (DxDiag)](https://support.microsoft.com/en-us/windows/open-and-run-dxdiag-exe-dad7792c-2ad5-f6cd-5a37-bf92228dfd85)
in Windows to gather system information that might be helpful for
troubleshooting.

To use DxDiag to gather system information:

1. Press the **Windows key** + **R** to open the Run window. Type

   ```
   dxdiag /dontskip /whql:off /64bit /t %userprofile%/Desktop/DxDiag.txt
   ```

   then press **Enter**.

1. After 5-10 seconds, a file named `DxDiag.txt` will be created on the
   Desktop. This file contains information about the system.

If you prefer to use the graphical interface of DxDiag to gather system
information:

1. Press the **Windows key** + **R** to open the Run window.

1. In the Run window, type `dxdiag` then press **Enter**.

1. Click **Save All Information** to save the system information to a text
   file.
