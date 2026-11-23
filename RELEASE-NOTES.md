# Quartz-Miner 1.0.12 FIX

## FIX — V3 device selection on mixed and laptop rigs

- Quartz checks the reported CUDA capability and full PCI address of each selected GPU. The startup inventory rejects duplicate indices or addresses, missing cards and malformed PCI identifiers. The mining log includes the PCI domain.
- The RTX 3050 A Laptop GPU (Ada 8.9) takes the native B24 route. The ordinary RTX 3050 Laptop GPU and the RTX 2050 reporting 8.6 take the Ampere compatibility route. These three laptop models still need on-hardware Quartz proofs and pool receipts.
- The RTX 4070 Ti and RTX 4080 SUPER retain their qualified V3 profiles. Other Ti, SUPER and Laptop variants undergo the local Rust check. The eight-model routing regression ran on CPU with synthetic device records. Physical RTX 30 and RTX 50 tests are pending.
