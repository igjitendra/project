---
name: screenshot-localizer
description: Localize visible text in app screenshots while preserving layout and producing store-ready exports. Use when translating App Store or Play Store screenshots.
---

# Screenshot Localizer

## Goal

Produce accurate localized screenshots that retain the original visual design and meet the requested store specifications.

## Required Inputs

Confirm the source screenshots, target locale or locales, output dimensions, platform, and any required terminology or translation glossary.

## Workflow

1. Inventory every source image and record its pixel dimensions.
2. Extract all visible text and preserve a source-to-translation mapping.
3. Translate for meaning, tone, locale conventions, and available space. Do not translate brand names unless instructed.
4. Rebuild only the text regions while preserving device frames, imagery, colors, gradients, shadows, spacing, and hierarchy.
5. Use appropriate fonts with glyph support and visually match weight, size, alignment, and line height.
6. Adjust text layout carefully for expansion or contraction without hiding important UI.
7. Export losslessly at the exact requested dimensions and naming convention.
8. Visually inspect every output at full size for clipping, overlap, mistranslation, font fallback, artifacts, and accidental cropping.

## Rules

- Never invent unreadable source text; ask for a clearer image.
- Do not stretch, blur, or unnecessarily recompress the source.
- Do not modify UI elements unrelated to localization.
- Preserve safe areas and store-required dimensions.
- Keep translated terminology consistent across the complete screenshot set.
- Never claim store readiness without checking dimensions and visually inspecting every export.

## Output

Place files in locale folders such as `screenshots/es/` and provide a manifest of source text, translation, dimensions, and completed QA.
