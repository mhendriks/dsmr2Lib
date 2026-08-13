# Changelog

All notable changes to Dsmr2Lib are documented in this file.

## [0.2.0] - 2026-08-13

### Added

- Add `P1PacketAccumulator` for accumulating a P1 telegram in a caller-supplied
  fixed-size buffer.
- Add `P1FixedReader<MaxTelegramLength>` as a heap-friendly alternative to the
  existing Arduino `String`-based `P1Reader`.
- Add `rawLength()` to both reader implementations.
- Document the fixed-buffer reader and its raw-data format.

### Changed

- Accept the 12-byte hexadecimal DLMS/COSEM date-time emitted by MCS301 meters
  and convert it to the existing DSMR timestamp representation.
- Treat the MCS301 M-Bus sentinels `()` (device type) and `(0)` (timestamped
  delivery value) as absent fields on M-Bus channels 1 through 4.
- Keep the bundled `read` and `parse_to_json` examples compatible with current
  ESP32 cores.

### Compatibility

- The existing `P1Reader` API remains available and compatible.
- Regular DSMR timestamps and non-empty M-Bus values continue to use the
  existing strict parsers.
