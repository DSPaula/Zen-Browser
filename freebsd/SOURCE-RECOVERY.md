# Source Recovery — verified FreeBSD 14.5 environment

> **Scope:** This is an optional recovery path for one tested native build. It is not a general-purpose patch for every FreeBSD system and must not be assumed compatible with other OS versions, architectures, machines, toolchains, or Firefox/Zen snapshots.

## Verified environment

- OS: FreeBSD 14.5-RELEASE-p1
- Architecture: amd64 (x86_64)
- Build toolchain: LLVM 19
- Computer: HP 450 Notebook PC
- Product number: C9K33LT#ABM
- CPU in the verified configuration: Intel Core i3-2328M, 2 cores / 4 threads, 2.20 GHz
- Chipset: Intel HM75
- Source: Zen Browser desktop source with its Firefox Nightly-based engine
- Firefox engine milestone of the successful build: 157.0
- Build metadata: Zen 1.0.0; BuildID `20261010134540`; SourceStamp `84a8300ff8579c91c9587990f6b13e32b994e5ca`

These details describe the configuration in which the build was verified. They do not guarantee that the same changes will work unchanged on another computer or Nightly snapshot. This document describes a Zen/Firefox engine source tree; it does not mean that the delta is a patch for a separately installed Firefox Nightly package.

## Engine base revision

The modified `zen-browser/desktop` engine was based on revision `d3ec66377c`, before the Zen/FreeBSD engine changes. The successful native build was produced after applying the relevant Zen patch set and FreeBSD Firefox patches.

## Recovery archive

- Archive: `zen-engine-functional-delta.tar.gz`
- Size: 13,193,516 bytes
- Tracked-file binary patch: 4,326,658 bytes
- Additional untracked source/resource files: 181
- Backup `.bak` files and build artifacts excluded

The archive contains `engine.patch`, a binary-capable Git diff from the exact base revision, and `untracked/`, containing 181 additional source/resource files with their relative paths preserved. The paths were compared against the working tree.

## Optional recovery procedure

Use this only if the normal fork source fails to reproduce the verified behavior and you need to reconstruct the known-good engine state.

1. Check out a clean engine tree at exactly `d3ec66377c`.
2. Extract the archive outside the engine directory.
3. From the engine root, apply the patch: `git apply --binary /path/to/extracted/engine.patch`.
4. Copy the contents of the archive's `untracked/` directory into the engine root, preserving relative paths.
5. Check the applicable Zen and FreeBSD patches against this source revision before building. Stop and investigate if they do not apply cleanly.

Do not restore `.bak` files. Do not apply this delta to another engine revision without reviewing compatibility first.

## Compatibility limits

This is a functional delta against one exact engine revision, not a complete Firefox/Zen source tree. The base source must be obtained separately at `d3ec66377c`. Only the environment listed above is documented as verified. Other FreeBSD releases, CPU architectures, machines, LLVM versions, or Firefox Nightly/Zen snapshots may require changes and separate testing.

## Artifact location

The recovery archive remains on the legacy `DSPaula/Zen-Browser-FreeBSD` repository, branch `publish-recovery`, separate from the normal source branch. See the recovery branch and archive there. Keeping it separate leaves the ordinary installation path unchanged while providing a clearly scoped recovery option.
