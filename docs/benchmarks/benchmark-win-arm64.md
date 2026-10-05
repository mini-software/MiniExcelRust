# MiniExcelRust benchmark (win-arm64)

- Date (UTC): 2026-10-05T10:25:30.8051329Z
- OS: Microsoft Windows 10.0.26200
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
| Cold | MiniExcelV2 | 2959.52 | 937.48 | 1554.13 | 46.27 | 17.09 | 1x |
| Cold | MiniExcelRust | 1067.56 | 346.35 | 111.54 | 34.3 | 12.99 | 2.77x |
| Warm | MiniExcelV2 | 6642.78 | 543.02 | 4677.76 | 49.52 | 20.52 | 1x |
| Warm | MiniExcelRust | 2937.79 | 339.09 | 304.99 | 37.08 | 16.19 | 2.26x |

Managed allocation excludes allocations made inside Rust. Peak working set and peak private bytes include the complete process.
