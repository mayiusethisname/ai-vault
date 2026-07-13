---
name: pdf-processing
description: Use when working with PDF files: reading, extracting text or tables, merging, splitting, rotating, OCR, creating PDFs, filling forms, extracting images, watermarking, or converting PDF content for analysis.
---

# PDF Processing

Choose the simplest reliable tool for the PDF task. Verify the output because PDF layout and scanned text are often messy.

## Tool Selection

- Text extraction: use `pdfplumber` first when layout or tables matter.
- Basic page operations: use `pypdf` for merge, split, rotate, metadata, encryption.
- Table extraction: use `pdfplumber`, then clean with `pandas`.
- OCR: convert pages to images and use OCR only when text extraction fails.
- PDF creation: use `reportlab` for simple generated PDFs.
- Image extraction: use `pdfimages` or a dedicated library if available.

## Workflow

1. Inspect the PDF type: text-based, scanned, form, image-heavy, or mixed.
2. Test extraction on 1-2 pages before processing the whole file.
3. Preserve page numbers in extracted output.
4. For tables, inspect raw rows before converting to a spreadsheet.
5. Save intermediate text/CSV files when they help review quality.
6. Verify output by sampling pages and edge cases.

## Common Checks

- Did text extraction preserve reading order?
- Are headers/footers polluting the content?
- Are table columns shifted or merged?
- Is OCR needed for scanned pages?
- Are page counts correct after split/merge/rotate?

## Cautions

PDFs are not structured documents. Do not assume visual layout equals clean text order. For legal, financial, or evidence-sensitive work, quote page numbers and keep the original file available.
