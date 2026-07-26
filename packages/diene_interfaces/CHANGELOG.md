## 1.0.0 (2026-07-26)

### ✨ Features ✨

- **dart-interfaces:** seed diene_interfaces mirror ([62fc02a](https://github.com/AtomiCloud/diene.dart_interfaces/commit/62fc02ac2ff53c09c8316bde8935e100dfebcc44))

# Changelog

All notable changes to this package are documented here. Releases are managed
from conventional commits by the repository release workflow.

## 1.0.0

- Add the S33 common-interface seams for Dart: `System` (environment, working
  directory, UTC clock, delay), `Vfs` (existence, stat, byte/text IO, listing,
  directory creation, deletion), `Terminal` (process execution plus interactive
  stdio), `LoggerSink`, and `MetricsCollector`.
- Report every expected failure as a `Result` value carrying the canonical
  RFC 9457 `Problem` from `diene_problems`, with the `type` URI minted only by
  the single C0 §2 builder (`PortName`, `PortErrorCode`, `portProblem`,
  `portFailure`, `invalidInput`).
- Add reusable boundary validators: `checkVfsPath`, `checkTerminalCommand`,
  `checkTerminalOutput`, `checkTerminalWrite`, `checkTerminalRead`,
  `checkLogRecord`, `checkMetricRecord`, and `checkTelemetryAttributes`.
- Ship the dependency-light `test_helper.dart` sub-library: in-memory fakes for
  all five seams with FIFO scripted fault injection, plus `expectPortProblem`
  and `SeamAssertionFailure`.
- Bind the frozen C0 release `c0-fixtures-r2` §2 Problem schema through a
  generated, digest-pinned projection.
- Own no trace seam and no OTel implementer: Dart and Flutter telemetry rides
  Faro at runtime through the frontend machinery.
