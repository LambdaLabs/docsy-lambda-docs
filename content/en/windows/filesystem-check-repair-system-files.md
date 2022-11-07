---
title: "How do I run a filesystem check on Windows and repair system files?"
type: docs
tags:
- troubleshooting
---

If Windows is freezing or behaving erratically, there might be a problem with
the filesystem or system files. Examples of erratic behavior include:

- blue screens
- crashing applications
- sluggish performance
- failed Windows updates

You can use the built-in
[Deployment Image Servicing and Management (DISM)](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/what-is-dism?view=windows-10)
and System File Checker (SFC) tools to try to fix the problem.

To use the DISM tool to fix problems with the filesystem or system files:

1. Press the **Windows key** + **R** to open the Run window.

1. In the Run window, type `cmd` then press **Ctrl** + **Shift** + **Enter**.

   This command opens the Command Prompt window with elevated (admin)
   privileges.

1. In the Command Prompt window, run the command:

   ```
   DISM.exe /Online /Cleanup-Image /RestoreHealth
   ```

   This command performs cleanup and recovery operations on the system files.
   For more information, see
   Microsoft's documentation on [repairing a Windows image](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/repair-a-windows-image?view=windows-10).

1. After `DISM.exe` finishes, run the following command in the Command Prompt
   window: `sfc /scannow`. This command scans all protected system files and
   replaces corrupted files. For more information, see Microsoft's
   documentation on
   [using SFC to repair missing or corrupted system files](https://support.microsoft.com/en-us/topic/use-the-system-file-checker-tool-to-repair-missing-or-corrupted-system-files-79aa86cb-ca52-166a-92a3-966e85d4094e).

Run the `sfc /scannow` command up to 3 times until you receive the message:
`Windows Resource Protection did not find any integrity violations.`

{{% alert title="Note" color="info" %}}
If after running this command 3 times you do not receive the message `Windows
Resource Protection did not find any integrity violations`, it is unlikely
that a problem with the filesystem or system files is the cause of Windows
freezing or behaving erratically.
{{% /alert %}}

Reboot the machine and test to see if Windows continues to freeze or behave
erratically.
