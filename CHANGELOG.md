# Changelog

## v1.0.2 (2026-01-28)

### Domain Migration

- Migrated all references from `defcoin-ng.org` to `defcoin.io` across the codebase
  - README, man pages, `configure.ac`, `init.cpp`, `guiconstants.h`, `contrib/README.md`, `doc/README.md`

### Chain State Updates (2026-01-11)

- Updated `nMinimumChainWork` to match current chain state
- Updated `defaultAssumeValid` to block 2186382
- Added checkpoint for block 2186382
- Updated `chainTxData` with current transaction count (798,434 txns)

### DNS Seeds and Network

- Added new primary DNS seeds: `seed.defcoin.io`, `seed2.defcoin.io`
- Retained legacy seeds as fallbacks: `seed.defcoin-ng.org`, `seed2.defcoin-ng.org`, `seed.defcoin.mikej.tech`
- Updated testnet primary seed to `test.defcoin.io`, retained `test.defcoin-ng.org` as fallback
- Updated hardcoded seed IPs in `chainparamsseeds.h`

### Version and Build

- Bumped version from 1.0.0 to 1.0.2
- Updated copyright year to 2026
- Simplified version string format (removed git hash suffix from `clientversion.cpp`)
- Added `fix-mingw-file-id-info.patch` for Qt MinGW cross-compilation fix

### Debug Window Enhancements

- Added "Network Health" section to the Information tab:
  - Difficulty (current PoW difficulty)
  - Network hash rate (estimated from last 120 blocks, auto-scaled units)
  - Chain tips (active chain + fork count)
  - Sync progress (percentage)
- Added per-message-type traffic stats to peer detail panel (top 5 by bytes for sent/received)
- Network health fields update automatically when new blocks arrive

### Compiler Compatibility Fixes

- Added `#include <cstdint>` to `src/bench/bench.h` for newer compiler support
- Added `#include <stdexcept>` to `src/support/lockedpool.cpp` for newer compiler support

### Repository Cleanup

- Removed dead Travis CI badge from `README.md`
- Fixed typo in `README.md` ("sofware" → "software")
- Added `release-windows/` to `.gitignore`
- Added `!depends/patches/**` exception to `.gitignore` so Qt patches are not excluded by the `*.patch` rule
- Removed editor backup files (`configure~`, etc.)
- Normalized line endings for Windows build environment
