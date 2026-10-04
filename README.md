# Master CV

This repository is the source package for generating job-specific CVs with
ChatGPT, Claude, or another capable language model.

It keeps complete career information separate from the final résumé. For each
application, the model should read the master data, select the evidence most
relevant to the job description, and place it into the supplied ATS-friendly
HTML template before delivering a finished PDF. It must not copy the complete
master skill or project inventory into every CV.

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
6. The model must first propose relevant experience, skills, and projects and
   ask for your preferences. It must wait for your confirmation.
7. Tell it which projects to include and which skills or technologies to add,
   remove, or emphasize.
8. The model must generate and return the final A4 PDF. HTML is only an
   intermediate rendering format unless you explicitly request it.
9. Review every generated claim, date, metric, link, and page before applying.

## Example prompt

```text
Read instruction.md, master-cv.json, and cv-template.html from this repository.
First analyze the job description and propose only the relevant experience,
skills, and projects from master-cv.json. Do not generate the CV yet. Ask me to
confirm the target title, project count and selection, skill inclusions and
exclusions, missing information, and page preference.

After I confirm, create a highly tailored CV using only the approved relevant
content. Exclude unrelated technologies even if they exist in master-cv.json.
Preserve the layout in cv-template.html and return the finished A4 PDF as the
primary deliverable. Do not stop at HTML. Use one page when the approved
content fits comfortably; otherwise use two pages without shrinking the text
excessively.

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

## Tailoring behavior

- Inclusion is opt-in: every skill, bullet, and project must be relevant to the
  job description or explicitly requested by the user.
- The model must not dump the full master skill list into a targeted CV.
- For example, a networking CV should not contain React, Next.js, Tailwind CSS,
  or UI libraries unless the job description or user explicitly requests them.
- The model must ask for project count, selected technologies, exclusions, and
  missing truthful information before generating anything.
- Unsupported job requirements are reported as gaps rather than disguised with
  unrelated experience.
- The final deliverable is always a PDF aligned with the HTML template.

## Privacy

This repository is intended to be public. Do not commit private addresses,
identity numbers, passwords, API keys, confidential employer information, or
any contact detail that should not be permanently indexed.

## Data maintenance

Update `master-cv.json` when experience, education, skills, projects,
certifications, or awards change. Keep claims factual and measurable. If a
metric cannot be verified, omit it or mark it for confirmation rather than
guessing.
