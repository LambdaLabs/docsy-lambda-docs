---
title: "How do I prevent my system from suspending or sleeping?"
type: docs
tags:
- Ubuntu
---

To prevent your system from going to sleep or suspending, run:

```bash
sudo systemctl mask hibernate.target hybrid-sleep.target \
  suspend-then-hibernate.target sleep.target suspend.target
```
