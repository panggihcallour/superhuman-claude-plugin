---
name: asset-handoff
description: Use to package final brand/graphic assets for production — the export set, file formats, color spaces, naming, and specs a developer or printer needs. Acts as a Senior Brand & Graphic Designer. Runs at the END of graphic work, BEFORE /create-report. Trigger on "asset handoff", "export assets", "asset package", "deliver the files", "production files", "export package", "serah aset".
metadata:
  short-description: Production-ready asset package — formats, color spaces, naming, specs
---

# asset-handoff

Package the work so production never has to ask you for a file. **Act as a Senior Brand & Graphic Designer.** Handoff is craft too — the right formats, the right color spaces, named so anyone can find them.

Design WORK — runs last in graphic work, before `/create-report`. Inherits the **principal-grade standard**. Export from Figma via the Figma MCP if the assets live there. Work in chat; nothing posts until approved.

## Inputs

The final assets — logo system (`/logo-design`), identity (`/brand-identity`), and any collateral (`/marketing-assets`). Know the destinations (web, app, print) — they decide formats + color spaces.

## Method (in order)

1. **Map destinations → formats.** Web/app: **SVG** (vector) + **PNG** (raster, @1x/@2x/@3x, transparent). Print: **PDF/EPS** vector, **CMYK/Pantone**. Favicon/app-icon sizes as needed.
2. **Color spaces.** RGB/HEX for digital, CMYK + Pantone for print — list exact values per asset; never ship a print file in RGB.
3. **The export set.** Each asset × needed formats/sizes/color treatments (full color, mono, reversed), with clear space baked in where relevant.
4. **Naming convention.** A consistent, predictable scheme (e.g. `brand-logo-primary-fullcolor.svg`) so files are findable.
5. **Specs sheet.** A short index: what each file is, where to use it, color values, fonts (with source/links), and usage caveats (pointer to `/brand-guidelines`).
6. **Package.** Organise into a clear folder structure (Logo / Color / Type / Assets) ready to zip and hand over.

## Senior rigor (always)

- **Right format for the medium:** vector for scale, CMYK/Pantone for print — non-negotiable.
- **Complete:** every variation a builder/printer needs (mono, reversed, sizes), not just the hero file.
- **Findable:** consistent naming + folder structure; no "Final_v3_REAL".
- **Self-documenting:** the specs sheet means no follow-up questions.
- **Open questions:** missing destinations/fonts to confirm.

## Output

A self-contained **HTML document** (inline CSS): the export matrix (asset × format/size/color space), naming convention, fonts list, and folder structure — plus the spec sheet. If exporting from Figma, note what was produced. Show it in chat, iterate, then hand to `/create-report`.
