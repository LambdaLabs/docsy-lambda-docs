---
title: "Why am I seeing an error about NMI received for unknown reason?"
type: docs
---

You can safely disregard the error message: "Uhhuh. NMI received for unknown
reason […] ."

This error message might show up in, for example:

- The log file `/var/log/syslog`.
- The output of the command `dmesg`.
- The output of the command `journalctl`.

The error message results from a bug in AMD's newer processors, including
processors used in our servers. The bug has no impact other than causing the
"NMI received for unknown reason" error message to appear in system logs.
