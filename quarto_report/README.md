# Quarto Report Template

Template untuk laporan panjang dokumen interaktif menggunakan Quarto.

## Files

- `report.qmd` - Template laporan panjang dengan format dokumen
- `report.css` - Custom CSS untuk report dengan Computer Modern font (LaTeX-like)

## Features

**Report:**
- Long-form document format
- Multiple output formats: HTML, PDF
- Table of contents auto-generated
- Cross-references untuk tables, figures, equations
- Bibliography support dengan citations
- Code execution dan folding
- Professional academic styling
- Computer Modern fonts konsisten dengan LaTeX

## Usage

```bash
# Preview report (HTML)
quarto preview report.qmd

# Render ke HTML
quarto render report.qmd --to html

# Render ke PDF (butuh LaTeX)
quarto render report.qmd --to pdf

# Render both formats
quarto render report.qmd
```

## Font Configuration

Custom CSS menggunakan Computer Modern fonts yang sama dengan LaTeX.