# Quartz-Miner 1.0.12 FIX

## Latest FIX — dashboard status and per-GPU hashrate

- The dashboard shows local hashrate for each GPU alongside its share counters. Rates clear when mining stops.
- Accepted shares, verified settings and established pool connections are shown in green. Errors, rejected shares and stops are red. Pending actions and stale shares use amber.
- Fresh installations start with blank account fields and no selected or saved mining destination, custom pool or GPU profile. The built-in pool catalogue is available for setup.
- The package retains its V3 engine. The RTX 4070 Ti and RTX 4080 SUPER were tested on physical hardware with accepted V3 shares. Physical RTX 30 and RTX 50 qualification is pending. FP8 Ada and other unqualified V4 routes are disabled in the public package.
