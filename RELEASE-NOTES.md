# Quartz-Miner 1.0.12 FIX

## FIX — Multi-GPU startup and per-card results

- Several GPUs can run the two-second V3 compatibility check together. Each selected card gets the full test duration.
- Quartz matches each Rust verification receipt to the card's complete PCI address and model. Two identical cards must each provide their own result. Missing, duplicate or mismatched receipts prevent pool startup.
- The local dashboard and pool rate table identify each card by its PCI address. Mixed rigs retain one pool session and a separate CUDA image assignment for each card.

The packaged host and panel passed an offline five-card regression representing RTX 30, 40 and 50, including duplicate models on different PCI domains. On-hardware V3 qualification covers the RTX 4070 Ti and RTX 4080 SUPER. Physical RTX 30, RTX 50 and mixed-generation rig tests remain pending. RTX 20 is unsupported in this build. V4/FP8 remains experimental.

Download the [Windows x64 release and checksum](https://github.com/xxfalaxx/Quartz-Miner/releases/tag/v1.0.12).
