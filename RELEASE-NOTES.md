# Quartz-Miner 1.0.12 FIX

## Latest FIX — startup and GPU controls

- Fixes the B24 startup integrity mismatch and reports launch errors in the log.
- Confirms supported memory-clock and power-limit changes under load and restores session tuning on exit. Run the panel as administrator for GPU controls.
- The calibrated 890 mV profile recognizes the tested RTX 4070 Ti at its recorded PCI locations, at 2,580 or 2,610 MHz core. Loaded voltage may differ from the request.
- Confirmed settings use colors against NVIDIA-reported boost clocks or factory power.
- A clean package passed CPU panel checks. A short B24 HeroMiners test on the RTX 4070 Ti received one accepted share and no stale or rejected shares; this is not a long-duration stability test.

**Known limitation:** Other voltage points through MSI Afterburner require a writable V/F curve and remain unvalidated. Confirm the actual voltage under load.

Extract the Windows x64 ZIP into its own folder and open **Quartz-Miner.Panel.exe** as administrator. A new installation has no saved identities, destinations or tuning profiles. Keep **user-settings** when updating in place. Verify the ZIP against **SHA256SUMS.txt**.

**Windows ZIP SHA-256:** `1906109da3dfcbb390f1b2d974f69619e35697f1a63aecc2f8b5d029cdebd97b`
