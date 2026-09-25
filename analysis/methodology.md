# Methodology

## Experiment flow

1. Create/configure the VM on Proxmox VE.
2. Create/configure the VM on VMware Workstation.
3. Keep guest resources equivalent:
   - 2 vCPU
   - 2 GB RAM
   - 20 GB virtual disk
4. Install Ubuntu.
5. Verify CPU, memory and disk.
6. Install Sysbench.
7. Run the same CPU workload:
   `sysbench cpu --cpu-max-prime=20000 run`
8. Record execution time, events, events/sec and latency.
9. Compare the observations.
10. Preserve screenshots as evidence.

## Why the same workload matters

Using the same Sysbench command makes the benchmark workload consistent between the two VM runs.

## Why the configuration table matters

The configuration table allows an evaluator to verify that the allocated guest resources were intended to be equivalent.

## Reproducibility checklist

- [ ] Same Sysbench command
- [ ] Same prime limit
- [ ] Same thread count
- [ ] Same vCPU allocation
- [ ] Same RAM allocation
- [ ] Same virtual disk allocation
- [ ] Guest OS/version documented
- [ ] Host CPU documented
- [ ] Raw screenshots preserved
- [ ] Results stored in CSV
- [ ] Derived calculations shown
- [ ] Limitations stated
