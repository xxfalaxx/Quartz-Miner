# Quartz-Miner 1.0.12 FIX

## FIX — temperature target, manual restart and copyable log

- Enter a temperature goal in **GPU / Overclock** and apply it to one GPU or all compatible GPUs. Quartz controls each card's fans independently, increases airflow when warm, holds it around the target and gradually reduces it when cool. Actual temperature depends on the cooler, workload and ambient temperature.
- At a 60 °C goal, 61 °C increases airflow. The safety stop is 65 °C. The safety threshold is the lower of target + 5 °C and 75 °C. Missing temperature data also stops mining. Once the GPU cools, press **Start** to resume the applied destination. The log retains the stop reason.
- Select log rows and press **Ctrl+C**, or use **Copy log** for the complete visible history. Errors are red. Mining rate and session board power clear when stopped.
- Restored credential-free pool diagnostics, same-pool failover, Pool/Solo selection and exclusion of local test block candidates. The release retains per-PCI V3 selection on mixed rigs and the 30-second developer-fee window.
