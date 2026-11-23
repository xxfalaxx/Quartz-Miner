# Quartz-Miner 1.0.12 FIX

## FIX — Earlier developer fee windows

- The developer fee remains 1% of connected mining time. Quartz schedules up to 30 seconds after accruing 49 minutes 30 seconds of connected primary mining.
- Credit carries over after a normal stop. A failed fee connection leaves the credit available for a later attempt.
- The panel keeps primary and developer share counts separate and resumes the primary destination automatically.

Production mining uses Pearl V3. The RTX 4070 Ti and RTX 4080 SUPER have been tested on hardware. Physical RTX 50 qualification is pending. FP8/V4 remains experimental and disabled in production.

Download the Windows x64 ZIP and verify `SHA256SUMS.txt` on the [release page](https://github.com/xxfalaxx/Quartz-Miner/releases/tag/v1.0.12).
