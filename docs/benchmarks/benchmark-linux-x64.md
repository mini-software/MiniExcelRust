# MiniExcelRust benchmark (linux-x64)

- Date (UTC): 2026-10-05T10:24:42.1689905Z
- OS: Ubuntu 24.04.5 LTS
- Architecture: X64
- .NET SDK: 10.0.401
- Target framework: net10.0
- .NET runtime: .NET 10.0.12
- Baseline: MiniExcel 2.0.0-preview.4
- Candidate: MiniExcelRust 0.1.0-preview.2
- Workbook: 100000 rows x 10 columns
- Iterations: 5 fresh processes per runtime and scenario

| Scenario | Runtime | Elapsed (ms) | First row (ms) | Managed allocation (MB) | Peak working set (MB) | Peak private (MB) | Speedup |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Cold | MiniExcelV2 | 3170.31 | 1052.14 | 1554.01 | 139.35 | 193.34 | 1x |
| Cold | MiniExcelRust | 1253.79 | 351.68 | 114.08 | 124.09 | 189.99 | 2.53x |
| Warm | MiniExcelV2 | 6943.37 | 540.96 | 4674.16 | 143.5 | 200.56 | 1x |
| Warm | MiniExcelRust | 3110.59 | 339.48 | 304.99 | 128.88 | 195.02 | 2.23x |

Managed allocation excludes allocations made inside Rust. Peak working set and peak private bytes include the complete process.
