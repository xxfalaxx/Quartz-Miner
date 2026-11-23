# Quartz-Miner 1.0.12 FIX

## FIX — Pool diagnostics, Pool/Solo and copyable log

- Check all built-in pools, one selected server, or a custom TCP endpoint without entering a wallet or username. The panel shows the actual endpoint, transport, mode, latency and connection result.
- 2Miners now supports its shared Pool endpoints over TCP 1818 and TLS 11818, as well as its distinct Solo endpoints. Pool starts selected. Solo requires an explicit selection or loading a saved Solo destination. The selector is available for supported providers.
- The log displays errors, rejected shares, disconnects and failed checks in red. Use Ctrl+C for selected lines or **Copy log** for the history currently shown.
- All six built-in providers completed the connectivity check from a blank profile. 2Miners Pool/TCP, Pool/TLS and Solo accepted a synthetic authorization and supplied work. Local Rust Stratum tests passed. The live check submitted no shares.

Production mining uses Pearl V3. FP8/V4 remains experimental. Download the Windows x64 ZIP and verify `SHA256SUMS.txt` on the [release page](https://github.com/xxfalaxx/Quartz-Miner/releases/tag/v1.0.12).
