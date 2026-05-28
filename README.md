# Chani Disassembler Project Files for Cryo's Dune

This project contains the `.chani` annotation databases for the original 1992 Cryo *Dune* (CD version 3.7) DOS binaries.

The original binaries themselves are not redistributed here, only the annotation databases describing them.

Place the binaries in the same folder as the `.chani` files.

## Annotation databases

Each `.chani` file is a annotation project produced and edited by the tools in [chani-rs](https://github.com/madmoose/chani-rs/). They carry code and data labels, type definitions, struct layouts and comments for the corresponding binary:

| File | Annotates |
|---|---|
| `cryo-dune-3.7-cd-dncdprg.chani` | `DNCDPRG.EXE` — main game executable, and `DNVGA.BIN`, the graphics driver |
| `cryo-dune-3.7-cd-dnsdb.chani`   | `DNSDB.BIN` — Sound Blaster/Creative .VOC PCM driver. |
| `cryo-dune-3.7-cd-dnadl.chani`   | `DNADL.BIN` — AdLib-only music/SFX driver. |

## Disassembly Listings

Generated html listings for these projects are available here:

[cryo-dune-3.7-cd-dncdprg.html](https://thomas.fach-pedersen.net/dune/cryo-dune-3.7-cd-dncdprg.html)

[cryo-dune-3.7-cd-dnsdb.html](https://thomas.fach-pedersen.net/dune/cryo-dune-3.7-cd-dnsdb.html)

[cryo-dune-3.7-cd-dnadl.html](https://thomas.fach-pedersen.net/dune/cryo-dune-3.7-cd-dnadl.html)

## Working with these files

From the repository root:

```bash
# Query the main database
chaniq cryo-dune-3.7-cd-dncdprg.chani func start
chaniq cryo-dune-3.7-cd-dncdprg.chani xref seg000:ca1b

# Set / update annotations
chaniq cryo-dune-3.7-cd-dncdprg.chani set <address> --name <new_name> --comment "Detailed comment"

# Disassemble using the project file
disasm cryo-dune-3.7-cd-dncdprg.chani
```
