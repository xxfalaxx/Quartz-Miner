# Quartz-Miner 1.0.12 FIX

## Latest FIX — portable settings and verified GPU controls

- A fresh extraction opens with empty payout, server, manual port, thermal target, tuning loss and overclock fields. Saved preferences belong to the installation's `user-settings` folder. Keep this folder when updating in place. When moving from an older release, **Import previous settings** is available in an empty installation.
- Core and VRAM clock edits work independently. The panel checks the requested power limit against the live NVIDIA reading and logs a persistent mismatch once. Voltage and core adjustments remain pending until telemetry confirms them under load. External V/F control requires an enabled, supported MSI Afterburner curve.
- On the RTX 4070 Ti, the panel applied 205 W before load and changed the limit to 200 W during local Pearl V3 work. Under load it reported 2,580 MHz core, 405 MHz VRAM and 900 mV. The fan target was 90%. Factory power (285 W) and automatic control of both fans were verified after stopping.
- CPU regression tests covered 14 empty configuration fields, per-installation isolation, all five saved OC values, three coin destinations, repeated telemetry mismatches and recovery, and the bundled B24 and SmartTune hosts.

**Windows ZIP SHA-256** `fb9a268f7ef3f7eb9ef96cb9317d2b25c0641cdf4661b47adf85e88f67e4d81b`
