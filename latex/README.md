# LaTeX Templates

Template untuk dokumen akademik dan laporan penelitian menggunakan LaTeX.

## Files

- `main.tex` - Template laporan penelitian dengan Computer Modern font (format internasional)
- `laporan_indonesia.tex` - Template laporan dengan Times New Roman font (format Indonesia)
- `references.bib` - File bibliography untuk citations
- `main.pdf` - Contoh output PDF

## Features

- Academic paper layout dengan berbagai format margin
- Bibliography support dengan biblatex (IEEE style)
- Code highlighting dengan listings package
- Professional table formatting dengan booktabs
- Hyperlinks dan metadata PDF
- Mendukung embed PlantUML diagrams
- Cross-platform compatibility (Windows, macOS, Linux)

## Installation

### Windows

**Option 1: MiKTeX (Recommended)**
```powershell
# Install dengan Chocolatey
choco install miktex

# Atau download installer dari https://miktex.org/download
```

**Option 2: TeX Live**
```powershell
# Download installer dari https://tug.org/texlive/acquire-netinst.html
# Install dengan semua packages (3-4 GB)
```

### macOS

**Option 1: MacTeX (Recommended)**
```bash
# Install dengan Homebrew
brew install --cask mactex

# Atau download dari https://tug.org/mactex/
```

**Option 2: BasicTeX (Minimal)**
```bash
# Install BasicTeX (lebih kecil)
brew install --cask basictex

# Install packages yang dibutuhkan
sudo tlmgr update --self
sudo tlmgr install biber biblatex
sudo tlmgr install listings xcolor booktabs
sudo tlmgr install geometry setspace fancyhdr
sudo tlmgr install enumitem float hyperref
sudo tlmgr install amsmath amsfonts amssymb
sudo tlmgr install mathptmx  # untuk Times New Roman
```

### Linux (Ubuntu/Debian)

**Full Installation (Recommended)**
```bash
# Install TeX Live lengkap
sudo apt update
sudo apt install texlive-full

# Alternatif lebih cepat dengan packages spesifik
sudo apt install texlive-latex-base \
                 texlive-latex-recommended \
                 texlive-latex-extra \
                 texlive-bibtex-extra \
                 biber \
                 texlive-fonts-recommended \
                 texlive-fonts-extra
```

**Arch Linux**
```bash
# Install dengan pacman
sudo pacman -S texlive-most texlive-bibtexextra biber

# Atau minimal
sudo pacman -S texlive-core texlive-latexextra biber
```

**CentOS/RHEL/Fedora**
```bash
# Fedora
sudo dnf install texlive-scheme-full

# CentOS/RHEL (enable EPEL first)
sudo yum install epel-release
sudo yum install texlive texlive-latex texlive-collection-*
```

## Usage

### Basic Compilation

```bash
# Template internasional (Computer Modern)
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex

# Template Indonesia (Times New Roman)
pdflatex laporan_indonesia.tex
biber laporan_indonesia
pdflatex laporan_indonesia.tex
pdflatex laporan_indonesia.tex
```

### Advanced: Using latexmk (Recommended)

```bash
# Install latexmk (usually included in full distributions)
# Ubuntu: sudo apt install latexmk
# macOS: included in MacTeX
# Windows: included in MiKTeX/TeX Live

# Auto-compile dengan latexmk
latexmk -pdf main.tex
latexmk -pdf laporan_indonesia.tex

# Watch mode (auto-recompile on file changes)
latexmk -pdf -pvc main.tex
```

### VS Code Integration

**Install Extensions:**
- LaTeX Workshop
- LaTeX Utilities

**VS Code settings.json:**
```json
{
    "latex-workshop.latex.tools": [
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-pdf",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk",
            "tools": ["latexmk"]
        }
    ]
}
```

## Troubleshooting

### Missing Packages Error
```bash
# Ubuntu/Debian
sudo apt install texlive-latex-extra

# macOS (BasicTeX)
sudo tlmgr install <package-name>

# Windows (MiKTeX)
# Packages install automatically, atau gunakan MiKTeX Console
```

### Font Issues (Times New Roman)
```bash
# Linux: Install MS fonts
sudo apt install ttf-mscorefonts-installer

# Atau gunakan package mathptmx (sudah included di template)
```

### Biber/Bibliography Issues
```bash
# Clear aux files dan recompile
rm *.aux *.bbl *.bcf *.blg *.run.xml
pdflatex document.tex
biber document
pdflatex document.tex
```

### Memory Issues (Large Documents)
```bash
# Increase memory limits
export max_print_line=1000
export error_line=254
export half_error_line=238
```

## Docker Alternative

Jika instalasi lokal bermasalah, gunakan Docker:

```bash
# Pull LaTeX Docker image
docker pull texlive/texlive:latest

# Compile dalam Docker
docker run --rm -v $(pwd):/workdir texlive/texlive pdflatex main.tex
docker run --rm -v $(pwd):/workdir texlive/texlive biber main
docker run --rm -v $(pwd):/workdir texlive/texlive pdflatex main.tex
```

## Template Differences

| Feature | main.tex | laporan_indonesia.tex |
|---------|----------|----------------------|
| Font | Computer Modern 12pt | Times New Roman 11pt |
| Margins | 2.5cm all sides | 4cm left, 3cm others |
| Spacing | 1.5 | 1.5 |
| Style | International | Indonesian academic |
| Headers | Lowercase sections | UPPERCASE SECTIONS |

## Customization

- Edit metadata di hyperref package untuk PDF properties
- Ganti author, title, date di bagian atas dokumen
- Tambah/kurangi sections sesuai kebutuhan
- Update references.bib untuk citations
- Modify geometry package untuk custom margins
- Change font dengan package yang berbeda (times, palatino, dll.)

## Performance Tips

1. **Use latexmk**: Auto-handles compilation sequence
2. **Clear aux files**: Saat ada masalah compilation
3. **Use draft mode**: `\documentclass[draft]{article}` untuk editing cepat
4. **Split large documents**: `\input{chapter1.tex}` untuk maintainability