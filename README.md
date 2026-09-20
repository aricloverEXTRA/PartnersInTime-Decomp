# Partners in Time Decomp

A decompilation project for the Nintendo DS game Mario & Luigi: Partners in Time (also referred to in this repository as `PiT`).

This repository contains the build system, extracted configuration data, and source layout needed to rebuild the game's ARM9 code from original ROM data. It is not a full game dump or asset pack; the original decrypted ROMs must be supplied separately.

## Project status

This is a work-in-progress decompilation setup. The repository includes:

- Nintendo DS game configuration for supported versions
- DSD/objdiff-based build tooling
- ARM9 linker and symbol relocation configuration
- Source and library layout for decompiled code
- Scripts for downloading and configuring required toolchain components

## Supported versions

The repository includes build configs for:

- USA: `baserom_PiT_usa.nds` (`89c9136db3c3975c451a907e8bd6861ce6b81557`)
- EUR: `baserom_PiT_eur.nds` (`ba4ec2f99b4f2e0047601552bccf00aa73e28701`)

These checksums are also stored in:

- `PiT_usa.sha1`
- `PiT_eur.sha1`

## Requirements

Before building, you need:

- Python 3
- A decrypted original ROM dump for one of the supported versions
- A working environment for the build tools used by the project

The project is configured to automatically fetch some tooling through the scripts in `tools/`, including:

- `dsd`
- `objdiff-cli`
- `mwccarm` / `mwldarm`
- `wibo` on non-Windows systems

## Repository layout

```text
.
├── config/
│   ├── eur/
│   └── usa/
├── extract/
│   └── README.md
├── include/
├── src/
│   └── nitro/
├── tools/
│   ├── configure.py
│   ├── download_tool.py
│   ├── get_platform.py
│   ├── m2ctx.py
│   ├── mangle.py
│   ├── ninja_syntax.py
│   ├── sha1.py
│   └── transform_dep.py
├── .gitignore
├── PiT_eur.sha1
├── PiT_usa.sha1
└── README.md
