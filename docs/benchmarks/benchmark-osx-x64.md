# MiniExcelRust benchmark (osx-x64)

- Date (UTC): 2026-10-05T10:27:33.2369540Z
- OS: macOS 15.7.9
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
| Cold | MiniExcelV2 | 5407.2 | 1674.9 | 1555.87 | 42.35 | 0 | 1x |
| Cold | MiniExcelRust | 2068.11 | 663.58 | 112.93 | 32.41 | 0 | 2.61x |
| Warm | MiniExcelV2 | 13027.56 | 1091.53 | 4675.23 | 43.6 | 0 | 1x |
| Warm | MiniExcelRust | 6474.98 | 635.08 | 304.99 | 32.18 | 0 | 2.01x |

Managed allocation excludes allocations made inside Rust. Peak working set and peak private bytes include the complete process.
