# MiniExcelRust benchmark (linux-arm64)

- Date (UTC): 2026-10-05T10:24:47.2516710Z
- OS: Ubuntu 24.04.5 LTS
- Architecture: Arm64
- .NET SDK: 10.0.401
- Target framework: net10.0
- .NET runtime: .NET 10.0.12
- Baseline: MiniExcel 2.0.0-preview.4
- Candidate: MiniExcelRust 0.1.0-preview.2
- Workbook: 100000 rows x 10 columns
- Iterations: 5 fresh processes per runtime and scenario

| Scenario | Runtime | Elapsed (ms) | First row (ms) | Managed allocation (MB) | Peak working set (MB) | Peak private (MB) | Speedup |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Cold | MiniExcelV2 | 3523.3 | 1049.37 | 1555.72 | 123.57 | 176.24 | 1x |
| Cold | MiniExcelRust | 1056.28 | 330.31 | 113.27 | 108.07 | 173.92 | 3.34x |
| Warm | MiniExcelV2 | 8141.35 | 573.92 | 4674.2 | 127.26 | 179.78 | 1x |
| Warm | MiniExcelRust | 2742.92 | 322.6 | 304.99 | 112.08 | 177.86 | 2.97x |

Managed allocation excludes allocations made inside Rust. Peak working set and peak private bytes include the complete process.
