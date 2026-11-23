# Quartz-Miner 1.0.12

## FIX — Stratum recovery and GPU reset

Quartz keeps mining after stale, orphaned, invalid, duplicate and other rejected shares. The log records the rejection reason when the pool supplies it. On a Stratum disconnect, Quartz checks the reachable endpoints of the same supported pool and tries them in TCP connection-latency order. The dashboard displays the connected endpoint.

A local replay confirmed that the RTX 4070 Ti and RTX 4080 SUPER resumed submitting work after rejected shares and a simulated disconnect. The alternate endpoint accepted 26 Rust-verified proofs. Factory reset also passed on both cards.

- **Reset GPU** is available under **GPU / Overclock** while mining is stopped. It restores the selected card's driver clock settings, board power limit and automatic fan control, and keeps saved profiles.
- The official CuTe B200 route compiled to native FP8 machine code for SM100a. B200 hardware verification remains pending. The public download continues to mine V3.

## Previous 1.0.12 changes

- Selects the V3 CUDA image per GPU. Qualified Ada cards retain B24 in mixed rigs.
- Rejects incompatible certificate requirements before dispatching V3 work and invalidates obsolete submission leases on incompatible jobs.
- Integrates experimental V4 FP8 routing and stale-proof handling. The RTX 4070 Ti passed local PearlGateway tests with Rust-verified proof submission, including a job change during CUDA execution. FP8 Ada is disabled in this production ZIP.
- RTX 4070 Ti and RTX 4080 SUPER were tested on physical hardware for V3. RTX 50 compatibility images are bundled for V3. Physical RTX 50 testing remains pending.
- Fresh installations have blank mining identity fields and no saved destinations or GPU profiles. The panel retains the 1% Dev-Fee notice.

Extract the Windows x64 ZIP and start `Quartz-Miner.Panel.exe`. Check the ZIP against the accompanying `SHA256SUMS.txt`.
