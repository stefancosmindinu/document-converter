# 📄 Document Converter

Python scripts to convert documents — simple, fast, from the terminal.

## Available Scripts

| Script | Conversion |
|---|---|
| `word_to_pdf.py` | Word (.docx/.doc) → PDF |
| `pdf_to_word.py` | PDF → Word (.docx) |
| `merge_pdf.py` | Merge multiple PDFs into one |

---

## Installation

### 1. Python dependencies
```bash
pip install pdf2docx pypdf
```

### 2. LibreOffice (required for word_to_pdf)
**Linux (Ubuntu/Debian):**
```bash
sudo apt install libreoffice
```
**Mac:**
```bash
brew install libreoffice
```
**Windows:**
Download from [libreoffice.org](https://www.libreoffice.org/)

---

## Usage

### Word → PDF

```bash
# Single file
python word_to_pdf.py document.docx

# Multiple files
python word_to_pdf.py file1.docx file2.docx

# All files in a folder
python word_to_pdf.py folder/

# With specific output folder
python word_to_pdf.py document.docx --output pdf_files/

# Using wildcard
python word_to_pdf.py *.docx
```

### PDF → Word

```bash
# Single file
python pdf_to_word.py document.pdf

# Multiple files
python pdf_to_word.py file1.pdf file2.pdf

# All PDFs in a folder
python pdf_to_word.py folder/

# With specific output folder
python pdf_to_word.py document.pdf --output word_files/

# Specific pages only (e.g. pages 1-3)
python pdf_to_word.py document.pdf --pages 1-3

# Specific pages (e.g. 1, 3 and 5)
python pdf_to_word.py document.pdf --pages 1,3,5
```

### Merge PDFs

```bash
# Merge specific files — order matters!
python merge_pdf.py file1.pdf file2.pdf file3.pdf

# With custom output name
python merge_pdf.py *.pdf --output complete_document.pdf

# All PDFs in a folder (alphabetical order)
python merge_pdf.py folder/

# Practical example
python merge_pdf.py report.pdf annex1.pdf annex2.pdf --output final_report.pdf
```

---

## Practical Examples

```bash
# Convert all Word documents in current folder to PDF
python word_to_pdf.py *.docx --output pdf/

# Convert a PDF to Word
python pdf_to_word.py report.pdf

# Convert only first 3 pages of a large PDF
python pdf_to_word.py large_document.pdf --pages 1-3

# Merge 3 PDFs into one
python merge_pdf.py cover.pdf content.pdf appendix.pdf --output full_document.pdf
```

---

## Notes

- **word_to_pdf.py** — very good quality, preserves original formatting
- **pdf_to_word.py** — quality depends on the PDF (scanned PDFs may not convert perfectly)
- **merge_pdf.py** — preserves all pages and formatting from each file
- Scanned PDFs (images) cannot be perfectly converted to Word without OCR
- Output files are saved in the same folder as the original (unless `--output` is specified)

---

## Requirements

- Python 3.7+
- LibreOffice (for word_to_pdf)
- `pip install pdf2docx pypdf` (for pdf_to_word and merge_pdf)
