# Omne Foundry

Local, reproducible toolchain drop for Omne contracts. Currently ships the
`pysub-compiler` built from `smart-contract-workshop/compiler`, staged here so
we always know which binary we're using.

## Current binary
- Source: `smart-contract-workshop/compiler`
- Built: `cargo build -p pysub-compiler --release`
- Installed: `bin/pysub-compiler`

## Usage
- Add to PATH for this shell:
  - `export PATH="$(pwd)/bin:$PATH"` (run from repo root)
- Or prefix commands:
  - `PYSUBC=$(pwd)/bin/pysub-compiler scripts/build_bxt_contract.sh --profile release`

## Build BXT Wasm
- `bin/build-bxt --blox-root /path/to/Blox --profile release`
- Optional metadata signing:
  - `bin/build-bxt --blox-root /path/to/Blox --signing-key /path/to/key`

## Build Blox Pay Wasm
- `bin/build-blox-pay --blox-root /path/to/Blox --profile release`
- Optional metadata signing:
  - `bin/build-blox-pay --blox-root /path/to/Blox --signing-key /path/to/key`

## Rebuild instructions
1) `cd smart-contract-workshop`
2) `cargo build -p pysub-compiler --release`
3) `cp target/release/pysub-compiler ../omne-foundry/bin/pysub-compiler`

Keep this directory as the canonical place to grab the compiler when building Omne contracts.
