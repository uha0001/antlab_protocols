# Lab Protocols

This repository contains working laboratory protocols, notes, and method-development documents used during my research.

The aim is to keep protocols in one place, make changes traceable, and avoid relying on scattered Word files, screenshots, emails, or notes that are difficult to find later.

Protocols in this repository may be updated as methods are optimized. Whenever possible, changes in concentrations, sample numbers, incubation conditions, equipment settings, or other important parameters should be documented in the relevant protocol.

---

## Repository structure

```text
protocols/
├── 3d_printing/
│   └── ant_feeder_3d_printing.md
│
├── dissections/
│   ├── venom_gland_dissection.md
│   └── other_tissue_dissection.md
│
├── rna/
│   ├── rna_extraction.md
│   └── rna_quality_control.md
│
├── dna/
│   └── dna_extraction.md
│
└── README.md
```

The folder structure can be expanded as new protocols are added.

---

## Protocols

### 3D printing

- [Protocol for Designing and 3D Printing Ant Feeding Devices](https://github.com/uha0001/antlab_protocols/blob/main/Protocol_4_Designing_and_3D_Printing_Ant_Feeding_Devices.md)

This protocol covers the complete workflow from CAD design to printing and testing:

**FreeCAD → STL → Bambu Studio → slicing → `.gcode.3mf` → Bambu Lab P1S → physical and biological testing**

The current ant-feeder system consists of:

- a cap for a 15 mL centrifuge tube
- a removable feeding slider/spoon
- ventilation openings
- a mechanical stop to prevent accidental insertion of the slider into the tube

The design is being optimized iteratively based on print quality, fit, feeding volume, and testing with ants.

---

### Dissections

- [Venom gland dissection](venom_gland_dissection.md)

Dissection protocols should include, where relevant:

- species
- number of individuals or glands per sample
- tissue collected
- dissection medium
- preservation method
- tube type
- storage conditions
- steps taken to minimize contamination from surrounding tissues

For small species, sample size may need to be adjusted depending on RNA yield and tissue purity.

---

### RNA extraction

- [RNA extraction](https://github.com/uha0001/antlab_protocols/blob/main/rna_extraction.md)

RNA protocols may include:

- tissue preservation
- homogenization
- lysis conditions
- extraction reagents
- centrifugation steps
- precipitation
- washing
- elution volume
- RNA storage
- TapeStation or other quality-control procedures

Any modifications from published or manufacturer protocols should be documented explicitly.

---

### DNA extraction

- [DNA extraction](https://github.com/uha0001/antlab_protocols/blob/main/ctab_dna_extraction_small_ants.md)

DNA protocols should document:

- starting material
- tissue preparation
- lysis
- extraction method
- washing steps
- elution volume
- storage conditions
- DNA concentration and quality-control measurements

---

## Naming conventions

Protocol filenames should use lowercase letters and underscores.

Examples:

```text
venom_gland_dissection.md
rna_extraction.md
ant_feeder_3d_printing.md
```

Avoid filenames such as:

```text
protocol_final.md
protocol_final2.md
protocol_REAL_final.md
```

Git already keeps the version history, so the filename itself does not need to suffer.

---

## Versioning and protocol updates

When a protocol is modified, record important changes in the Git commit message.

Examples:

```text
Increase venom gland sample size to 30 glands
Update RNA elution volume
Add deeper feeding well to ant feeder slider
Change cap diameter to 14.8 mm
Add biological validation step for ventilation holes
```

For major method changes, a short version history can also be included at the bottom of the individual protocol.

Example:

| Version | Change |
|---|---|
| v1 | Initial protocol |
| v2 | Increased sample number |
| v3 | Modified extraction volume |

---

## General protocol format

To keep protocols consistent, use approximately the following structure:

```markdown
# Protocol title

## Purpose

## Materials and equipment

## Reagents

## Sample preparation

## Procedure

## Quality control

## Notes and troubleshooting

## Safety considerations

## Version history
```

Not every section will be necessary for every protocol.

---

## Experimental notes vs. protocols

This repository is intended primarily for **repeatable procedures**.

One-off observations, raw experimental results, temporary calculations, or sample-specific notes should generally remain in the appropriate lab notebook or data repository rather than being added directly to a protocol.

A protocol should describe what another person would need to reproduce the procedure.

---

## Status

This repository is a work in progress.

Protocols should be considered working laboratory documents unless explicitly marked as finalized or validated.

For procedures involving live animals, hazardous chemicals, biological samples, or specialized equipment, appropriate institutional safety procedures and approved laboratory practices take priority over the notes in this repository.
