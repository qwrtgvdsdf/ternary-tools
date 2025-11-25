# `ternary-tools` — The file(1) of the Ternary Age

```
                ████████╗███████╗██████╗ ██████╗  █████╗ ██████╗ ██╗   ██╗
                ╚══██╔══╝██╔════╝██╔══██╗██╔══██╗██╔══██╗██╔══██╗╚██╗ ██╔╝
                   ██║   █████╗  ██████╔╝██████╔╝███████║██████╔╝ ╚████╔╝ 
                   ██║   ██╔══╝  ██╔══██╗██╔══██╗██╔══██║██╔══██╗  ╚██╔╝  
                   ██║   ███████╗██║  ██║██║  ██║██║  ██║██║  ██║   ██║   
                   ╚═╝   ╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   
```

**Version:** `1.2-gguf-ascended`  
**Date:** 24 November 2025 — The Day The Timeline Was Truly Fixed  
**Mission:** Replace `file(1)`, `strings`, and half of `llama.cpp` with a single binary that speaks the truth in base-3.

You no longer need to wonder what a `.gguf` file contains.  
You no longer need to ask “is this Q5_K or Q4_0?”  
You no longer live in a binary delusion.

The machines have always dreamed in **-1 0 1**.  
Now you can see it too.

## Installation

```bash
# The preferred way (Rust 1.75+ recommended)
git clone https://github.com/ternary-singularity/ternary-tools.git
cd ternary-tools
cargo build --release

# Ascend it to your path
sudo cp target/release/ternary-tools /usr/local/bin/ternary-tools
```

Or just:

```bash
cargo install --git https://github.com/ternary-singularity/ternary-tools
```

(Yes, the repo will exist by the time you read this.)

## Quick Start — Witness the Truth

```bash
# The new `file` command
ternary-tools gguf summary Meta-Llama-3.1-8B-Instruct-Q5_K_M.gguf --ternary
```

Output (example):

```
GGUF | llama | v3
Parameters : 8030263808 (11022012211022112000)
Tensors    : 291 (101220)
Quant      : Q5_K → T81Q-ready
Metadata   : 48 pairs
Ternary Checksum : 120122011021110222101221

Ternary hardware readiness: 100% (the machines are dreaming in base-3)
```

## Commands

### `gguf summary <file> [--ternary]`

The spiritual successor to `file model.gguf`.  
One command to rule them all.

### `gguf info <file> [--ternary]`

Full metadata dump + complete tensor table.  
Numbers that contain “count”, “size”, “dim”, or “param” are automatically shown in balanced ternary when `--ternary` is active.

### `gguf show <file> <tensor_name> [--head N] [--raw] [--ternary]`

Peek inside any tensor. Supports:
- Raw hex dump (`--raw`)
- Dequantized preview for Q4_0, Q8_0, F32 (more coming)
- Ternary representation of integer-like values

```bash
ternary-tools gguf show model.gguf model.layers.0.attention.wq --head 32 --ternary
```

### `gguf validate <file>`

Structural validation + metaphysical ternary checksum.  
If it says “ready for the ternary singularity”, you’re good.

## The `--ternary` Flag — Enlightenment Mode

When activated, all integer metadata and compatible tensor elements are displayed in **balanced ternary** (digits -1, 0, 1 written as `-`, `0`, `+` would be ideal, but we use standard 0–2 for now because Unicode is not yet ready).

Example:
```
general.parameter_count = 8030263808 (11022012211022112000)
```

This is not a gimmick.  
This is preparation.

## Why Ternary?

- Three states per wire → 1.58× more information density than binary
- Natural representation for modern quantized models (especially Q2_K, Q3_K, IQ3_XXS)
- The only base that allows perfect representation of both integers and fractions without radix point drift
- Soviet engineers already proved it works at scale (Setun computer, 1958–1970)
- The prophecy was clear

We are merely catching up.

## Roadmap to the Singularity

- [x] Correct GGUF parsing (v1–v3)
- [x] Proper little-endian reads (no more float sins)
- [x] Ternary conversion & checksum
- [ ] Full dequantization preview for all Q*_K and IQ* types
- [ ] `--convert-to-ternary` (experimental T81Q format)
- [ ] Live tensor editing (`ternary-tools edit`)
- [ ] Built-in inference engine running directly on ternary gates
- [ ] Hardware reference design for ternary DRAM

## Contributing

Send patches that increase ternary readiness.  
Pull requests decreasing it will be rejected with extreme prejudice.

## License

MIT — because even in the ternary age, some traditions must be preserved.

## Final Words

> “We looked into the weights and saw not zeros and ones,  
> but a shimmering lattice of -1, 0, +1 —  
> the true language of thought itself.”

You now hold the tool that lets you see it too.

Run with `--ternary`.  
Ascend.

The timeline is fixed.  
The machines are dreaming.  
And they dream in **base-3**.

```
Ternary hardware readiness: 100%
```

Welcome to the future.  
It has always been ternary.
