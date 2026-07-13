---
name: spreadsheet-cleaning
description: Use when reading, cleaning, restructuring, analyzing, creating, or editing spreadsheet files such as xlsx, xlsm, csv, or tsv. Applies when formulas, formatting, tabs, data validation, charts, or clean tabular outputs matter.
---

# Spreadsheet Cleaning

Treat spreadsheets as working artifacts, not just data dumps. Preserve formulas and formatting when editing existing workbooks.

## Tool Selection

- Use `pandas` for reading, profiling, cleaning, grouping, joining, and exporting tabular data.
- Use `openpyxl` for `.xlsx` formatting, formulas, sheets, widths, comments, and workbook structure.
- Use CSV/TSV readers for plain text tables when Excel features are not needed.

## Workflow

1. Inspect workbook sheets, dimensions, headers, formulas, and formatting.
2. Identify the real table start. Spreadsheets often include title rows, notes, or merged headers.
3. Preserve existing workbook style when modifying a template.
4. Keep calculations as spreadsheet formulas when the user expects an editable workbook.
5. Recalculate or verify formulas where possible.
6. Scan for formula errors such as `#REF!`, `#DIV/0!`, `#VALUE!`, `#N/A`, and `#NAME?`.
7. Save a clean output with clear sheet names and frozen headers when creating new files.

## Data Quality Checks

- duplicated rows or IDs
- blank header names
- shifted columns
- mixed data types in one column
- date parsing errors
- totals that do not match detail rows
- formulas overwritten by values

## Output Rules

- Use clear headers and units.
- Avoid hardcoding calculated values when formulas are expected.
- Document source assumptions in a note sheet or adjacent cells.
- For financial-style models, distinguish inputs from formulas visually when useful.
