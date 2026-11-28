# Quartz-Miner 1.0.12 FIX

## Latest FIX — Titanium multicoin and pool recovery

- Select a coin and regional server in **Pools & destinations**. A fresh installation opens with blank payout fields. Replace the files in the same installation folder to retain existing settings.
- After a transport failure, Quartz retries the selected server three times, waiting five seconds before each attempt. It then probes other eligible servers of the same pool and mode and chooses the reachable server with the lowest measured TCP latency.
- The packaged panel completed live stop/restart and developer-fee cycles on an RTX 4070 Ti with RPlant and HeroMiners. An isolated test ledger was seeded close to the fee boundary. Both pools accepted primary shares after restart. Both fans, clock locks and the factory power setting were restored.
- CPU verification passed 85 Rust tests, the three-coin WPF destination checks and a timed Pearl failover test using loopback servers.

**Windows ZIP SHA-256** `52ac5644514af693d83fffaa859c009103c9afca3cb8e127a3c7ed9a735421fa`
