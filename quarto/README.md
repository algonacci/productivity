# Quarto Templates

Template untuk presentasi dan dokumen interaktif menggunakan Quarto.

## Files

- `custom.qmd` - Template presentasi Quarto dengan reveal.js
- `custom.css` - Custom CSS untuk presentasi dengan Computer Modern font
- `report.qmd` - Template laporan panjang dengan format dokumen
- `report.css` - Custom CSS untuk report dengan Computer Modern font (LaTeX-like)

## Features

**Presentation (custom.qmd):**
- Reveal.js presentation dengan LaTeX-style fonts
- Computer Modern web fonts untuk konsistensi dengan LaTeX
- Chalkboard support untuk interaktif presentation
- Code highlighting dengan syntax highlighting
- Math equations dengan KaTeX
- Responsive images dan tables
- PlantUML diagram embedding

**Report (report.qmd):**
- Long-form document format (bukan presentasi)
- Multiple output formats: HTML, PDF
- Table of contents auto-generated
- Cross-references untuk tables, figures, equations
- Bibliography support dengan citations
- Code execution dan folding
- Professional academic styling
- Computer Modern fonts konsisten dengan LaTeX

## Usage

### Presentation

```bash
# Preview presentation
quarto preview custom.qmd

# Render ke HTML
quarto render custom.qmd

# Export ke PDF (butuh Chrome/Chromium)
quarto render custom.qmd --to revealjs-pdf
```

### Report

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

Custom CSS menggunakan Computer Modern fonts yang sama dengan LaTeX:
- Body: Computer Modern Serif
- Headers: Computer Modern Serif Bold
- Code: Computer Modern Typewriter
- Optimized spacing untuk readability