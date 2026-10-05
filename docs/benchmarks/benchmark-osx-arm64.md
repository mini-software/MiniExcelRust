# MiniExcelRust benchmark (osx-arm64)

- Date (UTC): 2026-10-05T10:25:20.5909470Z
- OS: macOS 26.6.2
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
| Cold | MiniExcelV2 | 3301.25 | 1149.86 | 1530.08 | 77.66 | 0 | 1x |
| Cold | MiniExcelRust | 1199.43 | 344.08 | 120.47 | 54.47 | 0 | 2.75x |
| Warm | MiniExcelV2 | 4750.31 | 568.14 | 4675.22 | 78.53 | 0 | 1x |
| Warm | MiniExcelRust | 3067.96 | 336.89 | 307.09 | 55.02 | 0 | 1.55x |

Managed allocation excludes allocations made inside Rust. Peak working set and peak private bytes include the complete process.
