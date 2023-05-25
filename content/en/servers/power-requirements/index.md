---
title: "What are the power requirements for my server's PSUs?"
type: docs
tags:
- hardware
---

The power requirements for Lambda server power supply units (PSUs) are as
follows:

| Manufacturer | Model        | Wattage | Voltage (AC) | Current (A) | Frequency (Hz) | Inlet/Outlet |
|--------------|--------------|---------|--------------|-------------|----------------|--------------|
| Supermicro   | PWS-2K08A-1R | 1800    | 200-220      | 10-9.8      | 60/50          | C14/C13      |
|              |              | 1980    | 220-230      | 10-9.8      | 60/50          |              |
|              |              | 2000    | 230-240      | 10-9.8      | 60/50          |              |
| Supermicro   | PWS-2K21G-2R | 2880    | 200-207      | 16-15.7     | 60/50          | C20/C19      |
|              |              | 3000    | 207.1-240    | 16-14.5     | 60/50          |              |

## Power connector inlets and outlets

This is what **C14 inlets** and **C13 outlets** look like:

{{< imgproc c14-c13-connectors Resize "400x" >}}{{< /imgproc >}}

This is what **C20 inlets** and **C19 outlets** look like:

{{< imgproc c20-c19-connectors Resize "400x" >}}{{< /imgproc >}}
