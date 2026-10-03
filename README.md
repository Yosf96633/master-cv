# Master CV

This repository is the source package for generating job-specific CVs with
ChatGPT, Claude, or another capable language model.

It keeps complete career information separate from the final résumé. For each
application, the model should read the master data, select the evidence most
relevant to the job description, and place it into the supplied ATS-friendly
HTML template.

## Repository files

| File | Purpose |
| --- | --- |
| [`master-cv.json`](master-cv.json) | Structured career data and the only approved factual source for generated CVs. |
| [`instruction.md`](instruction.md) | Rules the model must follow when tailoring a CV. |
| [`cv-template.html`](cv-template.html) | A4 HTML/CSS template modeled on the supplied CV design. It supports one or more pages. |
| [`template-preview-page-1.png`](template-preview-page-1.png) | Dummy first-page visual reference. |
| [`template-preview-page-2.png`](template-preview-page-2.png) | Dummy continuation-page visual reference. |
| [`pdf-json-audit.md`](pdf-json-audit.md) | Comparison of the earlier Software Engineer and AI Engineer PDFs with the master JSON. |

## Recommended workflow

1. Open a new ChatGPT or Claude conversation with web access.
2. Provide the public URL of this repository.
3. Provide the complete job description.
4. Ask the model to read `instruction.md` first.
5. Ask it to use `master-cv.json` as the factual source and
   `cv-template.html` as the required layout.
6. Review every generated claim, date, metric, and link before applying.
7. Export the final HTML to PDF using A4 paper size with browser headers and
   footers disabled.

## Example prompt

```text
Read instruction.md, master-cv.json, and cv-template.html from this repository.
Create a CV tailored to the job description below. Use only facts in
master-cv.json, preserve the supplied template, and return the completed HTML.
Use one page when the relevant content fits comfortably; otherwise use two
pages without shrinking the text excessively.

Job description:
[PASTE THE COMPLETE JOB DESCRIPTION HERE]
```

## Template characteristics

- A4 print layout
- Single-column reading order
- Conventional ATS section headings
- Selectable text rather than text embedded in graphics
- Plain contact links
- Right-aligned employment and education dates
- Controlled page breaks for multi-page CVs
- No icons, tables used for content, progress bars, or decorative sidebars

## Privacy

This repository is intended to be public. Do not commit private addresses,
identity numbers, passwords, API keys, confidential employer information, or
any contact detail that should not be permanently indexed.

## Data maintenance

Update `master-cv.json` when experience, education, skills, projects,
certifications, or awards change. Keep claims factual and measurable. If a
metric cannot be verified, omit it or mark it for confirmation rather than
guessing.

