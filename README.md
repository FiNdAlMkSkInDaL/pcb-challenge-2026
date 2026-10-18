# PCB Challenge 2026 — Finlay Phillips

Open `project/candidate.kicad_pro` using KiCad 10.0.6. The project includes the PCB, source schematic, portable available libraries and a report of missing original custom libraries. Embedded footprints remain present.

## Current status

This is an unfinished candidate. The latest saved native board has **47 unconnected items, 200 DRC errors and 366 warnings**. It is not a valid completed entry. This snapshot is frozen for the requested deadline. No final electrical or competition-compliance pass is claimed.

See `evidence/native-DRC.json` for actual findings, `LOGIC-DRAFT.md` for the circuit interpretation and its limits, and `PROVENANCE.md` for attribution and methods. Source footprints and literal nets are preserved. The known source courtyard and J3 findings remain unwaived except the exact official flip-flop exception, whose full applicability still needs review.

`SHA256SUMS.txt` records the current files. Packaging and matching hashes do not establish board validity.

## Circuit interpretation

The schematic is intended to implement a **four-word, four-bit FIFO with separate write and read clocks**. U10 has two address bits on each port, while three-bit read/write states supply an extra wrap bit for full/empty comparisons. The output path uses muxes and flip-flops before IO10–IO13. See [the logic deduction](LOGIC-DRAFT.md) for reference designators, the pointer equations and the exact scope of the retained checks. Memory semantics, inverted-output feedback, reset behaviour and clock-domain timing prevent claiming full functional correctness from this deduction alone.
