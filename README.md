# Resume

A LaTeX resume built with `pdflatex`.

## Prerequisites

### LaTeX Distribution

Install a LaTeX distribution that includes `pdflatex`:

- **Linux**: `sudo apt install texlive-full` (or `texlive-latex-extra` for a lighter install)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Windows**: [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/)

The following packages are required (included in most full distributions):

- `geometry`, `titlesec`, `enumitem`, `hyperref`
- `mathptmx` (Times New Roman font)
- `fontenc` (T1 encoding)
- `contour`, `ulem` (for the custom underline in the header)
- `xcolor`, `tabularx`

### VS Code (optional, for live preview)

1. Install the [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension.
2. Open `resume.tex` — the extension will detect it automatically.
3. Click the **View in VSCode tab** button (top right) or press `Ctrl+Alt+V` to open the PDF preview panel.
4. The PDF re-builds and refreshes automatically on save.

## Compiling

Run `pdflatex` from the project root:

```bash
pdflatex resume.tex
```

Run it **twice** if layout or spacing looks off — LaTeX sometimes needs a second pass to settle:

```bash
pdflatex resume.tex && pdflatex resume.tex
```

The output is `resume.pdf`. Build artifacts (`resume.aux`, `resume.log`, `resume.out`) are safe to ignore or delete.

> **Note:** Use `pdflatex` only. Do not switch to `xelatex` or `lualatex` without updating the font and encoding setup in the preamble.

## Previewing

- **VS Code**: Live preview via LaTeX Workshop (see above).
- **Linux**: `evince resume.pdf` or `okular resume.pdf`
- **macOS**: `open resume.pdf` (opens in Preview)
- **Windows**: double-click `resume.pdf` or open with your PDF viewer of choice
