# Quartz-Miner 1.0.12 FIX

## Latest FIX — flexible GPU tuning and model recommendations

- GPU tuning starts blank. Choose a saved profile or enter the settings you want to change. Empty fields preserve the current settings.
- Both Apply controls can change the core during mining. Native clock control passes the requested frequency to NVIDIA. The panel reports the measured clock under load. Explicit voltage still requires a supported driver calibration or an available V/F curve.
- **Load recommendation** fills an editable draft for the selected model. Quartz measurements supply the RTX 4070 Ti and RTX 4080 SUPER reference values. Other exact-model entries use the [PeakMiner OC Bench](https://oc.peakminer.org/) community snapshot. Community profiles fill core and power only. Apply the draft after reviewing it.
- V3 startup checks the driver resources by PCI on compatibility GPUs. Share replies are tracked by request ID and rejected shares are attributed by PCI where available. Physical RTX 30 and RTX 50 qualification is pending.

