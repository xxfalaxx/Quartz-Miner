# Quartz-Miner 1.0.12 FIX

## Latest FIX — dashboard, pool hashrate and GPU recovery

- The three coin cards display current prices, 24-hour change, chain height, difficulty, estimated network hashrate and block rewards when the sources publish them.
- A fresh Pearl installation prompts you to select a pool. Quantus reads the public HeroMiners pool total and NOID reads the public RPlant pool total. These readings are independent of the local GPU rate or worker rate.
- Quartz can complete a pending GPU restoration when a disabled, readable MSI Afterburner V/F curve already matches the verified original state. Leave **Force constant voltage** disabled.
- The clean Windows package passed 20 CPU checks and live Dashboard and pool-display checks without starting mining. The saved GPU recovery was verified on the idle RTX 4070 Ti.

Extract the entire Windows x64 ZIP and open **Quartz-Miner.Panel.exe**. Verify the archive against **SHA256SUMS.txt**. Keep **user-settings** when updating in place.

**Windows ZIP SHA-256** bf5684f9770b1084e275b0a0aa85f33caf1ae1872aa514db5a6c8fb711776721
