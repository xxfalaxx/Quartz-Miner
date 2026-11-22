# Quartz-Miner 1.0.12

- Selects the V3 CUDA image per GPU. Qualified Ada cards retain B24 in mixed rigs.
- Rejects incompatible certificate requirements before dispatching V3 work and invalidates obsolete submission leases on incompatible jobs.
- Integrates experimental V4 FP8 routing and stale-proof handling. The RTX 4070 Ti passed local PearlGateway tests with Rust-verified proof submission, including a job change during CUDA execution. FP8 Ada is disabled in this production ZIP.
- RTX 4070 Ti and RTX 4080 SUPER were tested on physical hardware for V3. RTX 50 compatibility images are bundled for V3. Physical RTX 50 testing remains pending.
- Fresh installations have blank mining identity fields and no saved destinations or GPU profiles. The panel retains the 1% Dev-Fee notice.

Extract the Windows x64 ZIP and start `Quartz-Miner.Panel.exe`. Check the ZIP against the accompanying `SHA256SUMS.txt`.
