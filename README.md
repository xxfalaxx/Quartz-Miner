# Quartz-Miner for Pearl V3-V4

![Quartz-Miner logo](images/logo.png)

Quartz-Miner is a Windows miner for Pearl (PRL) V3. Version 1.0.12 is optimized for **NVIDIA GeForce RTX 40 series**. The panel manages Stratum destinations, GPU selection, live telemetry, thermal limits, and named tuning profiles.

## NVIDIA GPU compatibility

| GPU family | Engine in 1.0.12 | Validation |
| --- | --- | --- |
| **RTX 4070 Ti and RTX 4080 SUPER** | Optimized B24 (Ada SM 8.9) | Both models tested on hardware with Rust-verified work and accepted Pearl V3 pool shares |
| **Other RTX 40 and Ada workstation GPUs** | Optimized B24 (Ada SM 8.9) | Physical testing on other models is pending. Quartz checks each selected model locally before pool mining |
| **RTX 30 and Ampere workstation GPUs** | Native CUDA compatibility mode | Driver and device checks apply. Physical Ampere testing is pending |
| **RTX 50 and Blackwell workstation GPUs** | Native CUDA compatibility mode | Driver and device checks apply. Physical RTX 50 and workstation testing is pending |
| **Hopper and Blackwell data center GPUs** | Native CUDA compatibility mode if the Windows driver supports the device | Device qualification is pending |
| **RTX 20, GTX, AMD and Intel** | Unsupported in this release | The packaged engine requires an Ampere-class CUDA device or later |

Quartz selects the CUDA image by each GPU’s PCI address. In a mixed rig, Ada GPUs keep the optimized B24 kernel while eligible Ampere, Hopper and Blackwell GPUs use the compatibility image. The panel verifies work from each compatibility GPU against Rust before starting pool mining. All selected GPUs share one Stratum connection.

**Mixed-rig test coverage.** A local Stratum test loaded both images on two physical Ada cards. The RTX 4080 SUPER ran B24 and the RTX 4070 Ti was deliberately assigned the compatibility image. An independent Rust verifier accepted 12 distinct proofs across the two cards. Physical rigs combining different GPU generations are still awaiting testing. [NVIDIA GPU compute capabilities](https://developer.nvidia.com/cuda/gpus)

Autotuning is available on the two qualified models. Clock, fan, voltage and power controls depend on the individual card and driver.

## Quick start

1. Download `Quartz-Miner-v1.0.12-win-x64.zip` and `SHA256SUMS.txt` from [Releases](https://github.com/xxfalaxx/Quartz-Miner/releases). Compare the archive hash with the published SHA-256.
2. Extract the entire ZIP to a local folder and open `Quartz-Miner.Panel.exe`. The package includes its .NET and Visual C++ runtimes. When Windows requests elevation, GPU controls use the administrator context.
3. Open **Mining destination**, select a pool and server, and enter your PRL wallet or that pool's supported mining username. Apply the destination and give it a name if you want to save it. The initial configuration is empty.
4. Choose your GPUs on the **Dashboard**. Run **Local test**, then **Start**. Use **GPU / Overclock** for per-card settings, model groups and thermal limits. **Reset this GPU** restores the driver defaults for that card.
5. Use **Stop** before closing the panel. The panel attempts to restore settings it applied for the mining session.

Windows x64 and a supported NVIDIA display driver are required. Driver 621.24 was used for qualification. NVIDIA driver branch R620 or later is recommended for the included CUDA 13.5 images. Normal mining uses the bundled runtimes and requires no CUDA Toolkit, Python, Rust, or separate .NET installation. The optional external voltage-curve control requires a compatible MSI Afterburner installation on cards without native calibrated voltage controls. [CUDA driver requirements](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/)

## Create a Pearl wallet

1. Download the Windows installer from [Pearl Research Labs' official desktop wallet release](https://github.com/pearl-research-labs/pearl/releases/tag/pearl-wallet-v3.0.0).
2. Open the wallet, create a new wallet, and follow the official guide to [back up your recovery phrase](https://help.pearlresearch.ai/hc/en-us/articles/49188981821457-Backing-up-your-wallet). Keep the phrase offline.
3. Copy a Pearl mainnet receiving address (typically `prl1p…`) and paste only that public address into **Mining destination**. If your pool uses a mining account instead, use the account format it specifies.

Use the [official Pearl block explorer](https://explorer.pearlresearch.ai/) to check a public address or block. Quartz-Miner never needs your recovery phrase or private keys.

## Pearl spot markets

- [SafeTrade · PEARL/USDT](https://safetrade.com/exchange/PEARL-USDT)
- [BigONE · PEARL/USDT](https://big.one/en/trade/PEARL-USDT)
- [Gate · PEARL/USDT](https://www.gate.com/trade/PEARL_USDT)

Look for Pearl Research Labs' **PEARL** asset. Some exchanges previously used **PRL**, which can also refer to a different asset. Check native Pearl deposit and withdrawal availability for your account before transferring.

## Panel update — November 22, 2026

- The mining-destination icon highlights the setup entry until a valid destination is applied.
- The mining log reports block candidates with GPU and height. The dashboard checks the most recent candidate's exact hash against the canonical block at that height. Older records without a block hash remain unverified.
- The sidebar displays the Pearl icon alongside the wallet balance.
- Live core control verifies the requested clock under load. Supported manual settings can be sent during mining. Voltage changes and large core increases ask for confirmation.
- Automatic fan control regulates each GPU independently. Simulated checks cover fan speed reduction below the limit and stopping at the limit or after losing telemetry.
- Autotuning shows live test data. A completed validation can be saved and applied to one or all validated GPUs. Stop mining before loading a new autotuned profile.

## Developer fee

The panel shows **1% Dev-Fee**. The engine schedules up to one minute of developer mining per 99 minutes of connected user mining. Pool charges are separate. Local tests do not mine to a pool.

## Panel

![Quartz-Miner dashboard with the tested RTX 4070 Ti and RTX 4080 SUPER detected](images/dashboard.png)

![Quartz-Miner GPU tuning and thermal controls](images/gpu-controls.png)

## Report a problem

Use [Issues → New issue](https://github.com/xxfalaxx/Quartz-Miner/issues/new/choose) and select **Bug report**. Include the release version, GPU model, NVIDIA driver and the steps to reproduce. Remove mining accounts, wallet addresses, credentials and private paths from attachments.
