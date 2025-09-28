# Markdown Templates

Template untuk dokumentasi dan reports menggunakan Markdown.

## Files

- `report.md` - Template basic report dalam Markdown format
- `markdown-pdf.css` - Custom CSS untuk VS Code Markdown PDF export

## Features

- Clean, readable format untuk dokumentasi
- GitHub-flavored Markdown support
- Mudah di-convert ke format lain (HTML, PDF, LaTeX)
- Support untuk tables, code blocks, dan images
- Compatible dengan static site generators

## Usage

### VS Code Markdown PDF Export

1. Install extension `Markdown PDF` (yzane.markdown-pdf)
2. Buka `report.md` di VS Code
3. Klik kanan → "Markdown PDF: Export (pdf)"

**Setup Custom CSS:**
1. Buka VS Code Settings (Ctrl+,)
2. Search "markdown-pdf"
3. Set `markdown-pdf.styles` ke: `["markdown-pdf.css"]`
4. Atau tambah di `settings.json`:
```json
{
    "markdown-pdf.styles": ["markdown-pdf.css"],
    "markdown-pdf.format": "A4",
    "markdown-pdf.margin.top": "2.5cm",
    "markdown-pdf.margin.bottom": "2.5cm",
    "markdown-pdf.margin.left": "2.5cm",
    "markdown-pdf.margin.right": "2.5cm"
}
```

### Alternative Methods

```bash
# Convert dengan Pandoc
pandoc report.md -o report.html
pandoc report.md -o report.pdf  # butuh LaTeX
pandoc report.md -o report.tex
```

## Integration

Markdown bisa dengan mudah di-integrate dengan:
- GitHub Pages / GitLab Pages
- Jekyll, Hugo, Gatsby static generators
- Documentation platforms (GitBook, Notion, etc.)
- Convert ke format lain dengan Pandoc

## Best Practices

- Gunakan heading hierarchy yang konsisten
- Include table of contents untuk dokumen panjang
- Embed images dengan relative paths
- Gunakan code blocks dengan language specification