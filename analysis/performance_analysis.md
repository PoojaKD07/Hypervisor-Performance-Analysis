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

## 3. What can be concluded

The supplied runs show:

1. Higher Sysbench throughput for the Proxmox VM.
2. Lower average latency for the Proxmox VM.
3. Lower maximum latency for the Proxmox run.
4. Nearly identical total benchmark duration.

## 4. What cannot be concluded

The data does **not** justify the statement:

> "Type-1 hypervisors are always faster than Type-2 hypervisors."

The experiment does not isolate hypervisor type because the underlying CPU environments shown in the evidence are different.

## 5. Evaluator-facing interpretation

A technically careful conclusion is:

> "With equivalent guest resource allocations and the same Sysbench CPU workload, the recorded Proxmox configuration achieved 1,749.16 events/sec compared with 1,460.03 events/sec for VMware Workstation. Average latency was 0.57 ms versus 0.68 ms. These are the observed results for the tested environments. Since the underlying host CPU environments were not identical, the results should not be interpreted as a controlled measurement of hypervisor overhead alone."
