---
title: "How do I prevent my system from suspending or sleeping?"
type: docs
tags:
- Ubuntu
---

To prevent your system from going to sleep or suspending, run:

```bash
sudo systemctl mask hybernate.target hybrid-sleep.target \
  suspend-then-hybernate.target sleep.target suspend.target
```
