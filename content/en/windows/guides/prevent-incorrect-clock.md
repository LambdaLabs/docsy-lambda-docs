---
title: "Prevent incorrect clock in Windows after booting Ubuntu"
type: docs
---

Ubuntu saves the current time to the machine hardware clock in
[UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time). Windows saves
the current time to the machine hardware clock in the local time. Because
Ubuntu and Windows save the current time to the machine hardware clock
differently, the current time displays incorrectly in Windows after booting
Ubuntu.

To fix this problem:

1. Press the **Windows key** + **R** to open the Run window. Type `cmd` then
   press **Ctrl** + **Shift** + **Enter**.

   This command opens the Command Prompt window with elevated (admin)
   privileges.

1. In the Command Prompt window, run the command:
   `reg add "HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation" /v RealTimeIsUniversal /d 1 /t REG_DWORD /f`.

   If Windows asks to update the clock due to DST (Daylight Savings Time), let
   Windows update the clock. The current time will be saved to the machine
   hardware clock in UTC but will display in Windows in the local time.

To learn more about this problem, see the
[Arch Linux documentation on system time](https://wiki.archlinux.org/title/System_time).
