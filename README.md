...existing code...
# Plasticity AppImage builder

This repository contains a small helper to build a self-contained AppImage of the Plasticity binary.

- Script: [`build_plasticity.sh`](build_plasticity.sh)
- Make target: [`makefile`](makefile)
- Ignore rule: [`.gitignore`](.gitignore)

## What it does
Downloads a Plasticity .deb, extracts the runtime files, collects dependent shared libraries, assembles an AppDir, and uses appimagetool to produce a distributable `.AppImage`.

## Requirements
- Linux (script assumes an Arch-based system using `pacman` for installing helper packages)
- sudo privileges
- `wget`, `ar`, `tar`, `ldd`, `cp`, `chmod`, `awk`, `file`
- network access to download the target .deb and appimagetool

## How to run
From the repository root:

- Using make:
  ```sh
  make
  ```

- Or run the script directly:
  ```sh
  ./build_plasticity.sh
  ```

The script will prompt at the end whether to remove the temporary build directory. The resulting `.AppImage` will be created in the repository root.

## Notes
- The script contains a disclaimer and performs operations with `sudo`.
- Edit `TARGET_DEB_URL` or `APPIMAGE_TOOL_URL` in [`build_plasticity.sh`](build_plasticity.sh) to change sources.
- The `.AppImage` file pattern is excluded via [`.gitignore`](.gitignore).
...existing code...