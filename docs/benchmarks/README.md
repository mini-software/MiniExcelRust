# Cross-platform benchmark results

Last updated (UTC): 2026-10-05 10:27:33

Each platform validates every returned row and cell before timing equivalent queries in alternating fresh processes.

| RID | Scenario | .NET runtime | MiniExcel | MiniExcel (ms) | MiniExcelRust (ms) | Speedup | Allocation reduction | Working-set reduction |
| --- | --- | --- | --- | ---: | ---: | ---: | ---: | ---: |
| [linux-arm64](benchmark-linux-arm64.md) | Cold | .NET 10.0.12 | 2.0.0-preview.4 | 3523.3 | 1056.28 | 3.34x | 92.7% | 12.5% |
| [linux-arm64](benchmark-linux-arm64.md) | Warm | .NET 10.0.12 | 2.0.0-preview.4 | 8141.35 | 2742.92 | 2.97x | 93.5% | 11.9% |
| [linux-x64](benchmark-linux-x64.md) | Cold | .NET 10.0.12 | 2.0.0-preview.4 | 3170.31 | 1253.79 | 2.53x | 92.7% | 11% |
| [linux-x64](benchmark-linux-x64.md) | Warm | .NET 10.0.12 | 2.0.0-preview.4 | 6943.37 | 3110.59 | 2.23x | 93.5% | 10.2% |
| [osx-arm64](benchmark-osx-arm64.md) | Cold | .NET 10.0.12 | 2.0.0-preview.4 | 3301.25 | 1199.43 | 2.75x | 92.1% | 29.9% |
| [osx-arm64](benchmark-osx-arm64.md) | Warm | .NET 10.0.12 | 2.0.0-preview.4 | 4750.31 | 3067.96 | 1.55x | 93.4% | 29.9% |
| [osx-x64](benchmark-osx-x64.md) | Cold | .NET 10.0.12 | 2.0.0-preview.4 | 5407.2 | 2068.11 | 2.61x | 92.7% | 23.5% |
| [osx-x64](benchmark-osx-x64.md) | Warm | .NET 10.0.12 | 2.0.0-preview.4 | 13027.56 | 6474.98 | 2.01x | 93.5% | 26.2% |
| [win-arm64](benchmark-win-arm64.md) | Cold | .NET 10.0.12 | 2.0.0-preview.4 | 2959.52 | 1067.56 | 2.77x | 92.8% | 25.9% |
| [win-arm64](benchmark-win-arm64.md) | Warm | .NET 10.0.12 | 2.0.0-preview.4 | 6642.78 | 2937.79 | 2.26x | 93.5% | 25.1% |
| [win-x64](benchmark-win-x64.md) | Cold | .NET 10.0.12 | 2.0.0-preview.4 | 2272.49 | 999.59 | 2.27x | 92.5% | 19.7% |
| [win-x64](benchmark-win-x64.md) | Warm | .NET 10.0.12 | 2.0.0-preview.4 | 3749.97 | 2685.23 | 1.4x | 93.5% | 18.8% |

Managed allocation excludes allocations made inside Rust. Each linked report includes peak process memory and environment metadata; the adjacent JSON contains every raw iteration and input hash.
