---
title: "How do I gather system information in Windows using MSINFO32?"
type: docs
tags:
- troubleshooting
---

You can use
[MSINFO32](https://support.microsoft.com/en-us/topic/description-of-microsoft-system-information-msinfo32-exe-tool-10d335d8-5834-90b4-8452-42c58e61f9fc),
also known as Microsoft System Information or Msinfo32.exe, to gather useful
information for troubleshooting your computer.

To use MSINFO32:

1. Press the **Windows key** + **R** to open the Run window. Type `cmd` then
   press **Ctrl** + **Shift** + **Enter** to open an elevated command prompt.

1. In the elevated command prompt, run:

   ```
   MSInfo32 /report %userprofile%/Desktop/sysinfo.txt
   ```

This will create a file on your Desktop named `sysinfo.txt` that contains
useful information about your computer.

{{% alert title="Note" color="info" %}}
You can additionally use [DxDiag]({{< relref "system-info-using-dxdiag" >}})
to gather useful information for troubleshooting.
{{% /alert %}}
