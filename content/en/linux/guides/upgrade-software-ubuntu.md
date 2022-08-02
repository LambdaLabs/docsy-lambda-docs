---
title: "Upgrade software in Ubuntu"
type: docs
---

Ubuntu regularly checks for new versions of software installed from an `apt`
repository, including:

- Ubuntu system updates
- Ubuntu security updates
- [Lambda Stack](https://lambdalabs.com/lambda-stack-deep-learning-software)

However, only Ubuntu security updates are automatically installed. Other
updates must be installed manually.

To manually check for and install new versions of software installed from an
`apt` repository, run the following commands in a terminal:

```bash
sudo apt-get update && sudo apt-get upgrade
```

{{% alert title="Note" color="info" %}}
Software that was installed from outside of an `apt` repository won't be
upgraded automatically or by running the above commands. Examples of software
installed from outside of an `apt` repository include:

- Software downloaded from a Git repository
- Software installed from a tarball
- Software built from source code
- Software installed using `pip`
- Software installed in Anaconda
- Software installed using `snap`
{{% /alert %}}
