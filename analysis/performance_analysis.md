# Performance Analysis

## 1. Raw results

| Metric | Type-1: Proxmox VE | Type-2: VMware Workstation |
|---|---:|---:|
| Execution time | 10.0005 s | 10.0001 s |
| Total events | 17,494 | 14,602 |
| Events/sec | 1,749.16 | 1,460.03 |
| Minimum latency | 0.57 ms | 0.65 ms |
| Average latency | 0.57 ms | 0.68 ms |
| Maximum latency | 2.43 ms | 10.14 ms |
| 95th percentile | 0.58 ms | 0.75 ms |

## 2. Derived comparison

### Throughput

Percentage difference relative to VMware:

```text
(1749.16 - 1460.03) / 1460.03 × 100
≈ 19.8%
```

Thus, the Proxmox run produced approximately 19.8% more events/sec.

### Average latency

```text
(0.68 - 0.57) / 0.68 × 100
≈ 16.2%
```

Thus, the Proxmox run had approximately 16.2% lower average latency.

### Maximum latency

```text
(10.14 - 2.43) / 10.14 × 100
≈ 76.0%
```

The maximum latency was lower in the Proxmox run by approximately 76% relative to the VMware value.

**Caution:** Maximum latency is particularly sensitive to transient system activity, scheduling and other environmental effects. It should not be treated as a standalone measure of hypervisor performance.

## 3. Performance Interpretation and Limitations

### Observed Results

The observed results show that the Proxmox VE configuration achieved **1,749.16 events/sec**, while VMware Workstation achieved **1,460.03 events/sec**.

The average latency was **0.57 ms** for Proxmox VE and **0.68 ms** for VMware Workstation.

The total execution times were approximately **10 seconds** for both configurations.

These results represent the performance observed in the tested configurations using the same Sysbench CPU workload.

### Limitations

The guest VM resource allocations were kept equivalent, with **2 vCPU, 2 GB RAM and 20 GB virtual disk** for both configurations.

However, the underlying host CPU environments shown in the experimental evidence were not identical. Therefore, the observed performance difference cannot be attributed to hypervisor type alone.

The results should therefore be interpreted as the performance observed for the tested configurations rather than as a universal statement about Type-1 and Type-2 hypervisors.
