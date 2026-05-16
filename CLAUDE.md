# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build

Compile the resume to PDF:

```bash
pdflatex resume.tex
```

Run twice if cross-references or layout need to settle. Build artifacts (`resume.aux`, `resume.log`, `resume.out`) are normal and can be ignored.

The template uses `mathptmx` (Times New Roman) and T1 font encoding — `pdflatex` is the intended compiler. Do not switch to `xelatex`/`lualatex` without also updating the font/encoding setup.

## Structure

Single file: `resume.tex`. All content and formatting live here.

**Custom macros defined in the preamble:**

| Macro | Purpose |
|---|---|
| `\resumeSubheading{org}{dates}{role}{location}` | Experience / education entry header (2-row tabular) |
| `\resumeProjectHeading{title \| tech}{dates}` | Project entry header |
| `\resumeItem{text}` | Bullet point inside an entry |
| `\resumeSubHeadingListStart/End` | Wraps a group of subheadings |
| `\resumeItemListStart/End` | Wraps bullet points within an entry |

**Section order:** EDUCATION → EXPERIENCE → PROJECTS → EXTRACURRICULAR ACTIVITIES → SKILLS

Each section follows the same pattern:
```latex
\section{SECTION NAME}
  \resumeSubHeadingListStart
    \resumeSubheading{...}{...}{...}{...}
      \resumeItemListStart
        \resumeItem{...}
      \resumeItemListEnd
  \resumeSubHeadingListEnd
```

## Formatting conventions

- `\myuline{text}` — custom underline command used for hyperlinks in the header (uses `contour` + `ulem` to avoid descender clipping).
- Special characters that must be escaped in bullet text: `&` → `\&`, `%` → `\%`, `$` → `\$`.
- Monetary values like `\$5,000` need the backslash-escaped dollar sign.
- The document is letterpaper, 11pt, with custom narrow margins (±0.6in horizontal, −0.9in top).
