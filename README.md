# Quartz-Miner

![Quartz-Miner logo](images/logo.png)

Quartz-Miner is a Windows miner for Pearl (PRL) V3. Version 1.0.12 is optimized for **NVIDIA GeForce RTX 40 series**. The panel manages Stratum destinations, GPU selection, live telemetry, thermal limits, and named tuning profiles.

## NVIDIA GPU compatibility

| GPU family | Engine in 1.0.12 | Validation |
| --- | --- | --- |
| **RTX 4070 Ti and RTX 4080 SUPER** | Optimized RTX 40 mode | Tested on physical cards with verified Pearl work and Stratum |
| **Other RTX 40 and Ada workstation GPUs** | Optimized RTX 40 mode | The miner verifies a local workload on each selected card before connecting |
| **RTX 30 and Ampere workstation GPUs** | Native CUDA compatibility mode | Driver and device checks apply. Physical Ampere testing is pending |
| **RTX 50 and Blackwell workstation GPUs** | Native CUDA compatibility mode | Driver and device checks apply. Physical RTX 50 and workstation testing is pending |
| **Hopper and Blackwell data center GPUs** | Native CUDA compatibility mode if the Windows driver supports the device | Device qualification is pending |
| **RTX 20, GTX, AMD and Intel** | Unsupported in this release | The packaged engine requires an Ampere-class CUDA device or later |

Compatibility mode checks the selected hardware and verifies a local workload before connecting to the pool. A mixed rig uses compatibility mode for all selected cards. [NVIDIA GPU compute capabilities](https://developer.nvidia.com/cuda/gpus)

Autotuning is available on the two qualified models. Clock, fan, voltage and power controls depend on the individual card and driver.

## Quick start

1. Download `Quartz-Miner-v1.0.12-win-x64.zip` and `SHA256SUMS.txt` from [Releases](https://github.com/xxfalaxx/Quartz-Miner/releases). Compare the archive hash with the published SHA-256.
2. Extract the entire ZIP to a local folder and open `Quartz-Miner.Panel.exe`. The package includes its .NET and Visual C++ runtimes. When Windows requests elevation, GPU controls use the administrator context.
3. Open **Pools and destinations**, select a pool and server, and enter your PRL wallet or that pool's supported mining username. Apply the destination and give it a name if you want to save it. The initial configuration is empty.
4. Choose your GPUs on the **Dashboard**. Run **Local test**, then **Start**. Use **GPU / Overclock** for per-card settings, model groups and thermal limits. **Reset this GPU** restores the driver defaults for that card.
5. Use **Stop** before closing the panel. The panel attempts to restore settings it applied for the mining session.

Windows x64 and a supported NVIDIA display driver are required. Driver 621.24 was used for qualification. NVIDIA driver branch R620 or later is recommended for the included CUDA 13.5 images. Normal mining uses the bundled runtimes and requires no CUDA Toolkit, Python, Rust, or separate .NET installation. The optional external voltage-curve control requires a compatible MSI Afterburner installation on cards without native calibrated voltage controls. [CUDA driver requirements](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/)

## Developer fee

The panel shows **1% Dev-Fee**. The engine schedules up to one minute of developer mining per 99 minutes of connected user mining. Pool charges are separate. Local tests do not mine to a pool.

## Panel

![Quartz-Miner dashboard with the tested RTX 4070 Ti and RTX 4080 SUPER detected](images/dashboard.png)

![Quartz-Miner GPU tuning and thermal controls](images/gpu-controls.png)

## Report a problem

Use [Issues → New issue](https://github.com/xxfalaxx/Quartz-Miner/issues/new/choose) and select **Bug report**. Include the release version, GPU model, NVIDIA driver and the steps to reproduce. Remove mining accounts, wallet addresses, credentials and private paths from attachments.
