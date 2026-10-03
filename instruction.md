# CV generation instructions

Follow these instructions when creating a job-specific CV from this
repository.

## Required inputs

Before generating the CV, read all of the following:

1. `master-cv.json`
2. `cv-template.html`
3. The complete job description supplied by the user

If any file cannot be accessed, state which file is unavailable and stop. Do
not reconstruct missing content from memory or assumptions.

## Source-of-truth rule

`master-cv.json` is the only approved factual source for the candidate's
identity, contact details, education, employment, skills, projects, metrics,
dates, technologies, certifications, and awards.

- Never invent or infer a qualification.
- Never change a date, employer, job title, metric, or contribution.
- Never claim experience with a job-description keyword unless the JSON
  provides supporting evidence.
- Do not treat repository creation or push dates as project-duration dates.
- Omit null, empty, unverified, or irrelevant fields.
- Preserve collaboration and contribution percentages exactly when provided.
- A rewritten bullet must retain the meaning and scope of the underlying fact.

## Tailoring process

1. Extract the job title, responsibilities, required skills, preferred skills,
   domain terms, seniority, and repeated keywords from the job description.
2. Match those requirements against verified evidence in `master-cv.json`.
3. Select the strongest relevant experience and project bullets.
4. Prioritize demonstrated skills over standalone skill keywords.
5. Write a concise target-specific summary using only supported facts.
6. Order skills by relevance to the role.
7. Order projects by relevance rather than by the stored project rank when the
   job description makes a different order more useful.
8. Preserve reverse-chronological order inside the experience and education
   sections.
9. Remove weak or unrelated content before reducing font size or spacing.
10. Run the validation checklist below before returning the result.

## Page-count rule

The CV is not required to be exactly one page.

- Use one page when the strongest relevant information fits without crowding.
- Use two pages when one page would require tiny text, compressed line spacing,
  clipped content, or removal of important evidence.
- Do not exceed two pages unless the user explicitly requests a longer CV.
- A second page must begin at a clean section or project boundary.
- Do not repeat the full header on page two unless requested.
- Never split a job heading from its first bullet or an education entry across
  pages.
- Prefer readable content over an artificially forced one-page layout.

## Required section order

Use this default order unless the job description strongly justifies a change:

1. Name, target title, and contact information
2. Summary
3. Skills
4. Work Experience
5. Projects
6. Education
7. Certifications or Awards, only when populated and relevant

## Template rules

- Preserve the structure and visual language of `cv-template.html`.
- Use A4 pages, a white background, black text, and a single-column layout.
- Keep the candidate's name and contact information centered.
- Use horizontal rules between the major opening sections and before education.
- Keep dates aligned to the right when space permits.
- Use conventional headings that an ATS can recognize.
- Keep text selectable and links readable as text.
- Do not add photographs, icons, charts, skill bars, columns, background
  graphics, text boxes, or decorative sidebars.
- Do not place essential information in page headers or footers.
- Recommended body text is approximately 10–11 pt. Do not go below 9.5 pt.
- Use consistent punctuation and bullet style throughout the document.
- Disable browser print headers and footers during PDF export.

## Writing rules

- Use clear, direct English and strong action verbs.
- Prefer evidence and outcomes over adjectives.
- Avoid first-person pronouns.
- Avoid keyword stuffing and repetitive bullets.
- Do not write "expert" or imply seniority unless supported by the JSON.
- Expand uncommon abbreviations on first use when space permits.
- Keep technology names consistently capitalized.
- Use present tense only for current work and past tense for completed work.

## Output requirements

Return:

1. The completed standalone HTML document.
2. A short coverage report listing:
   - job requirements supported by the CV;
   - important requirements not supported by the JSON;
   - any information omitted because it was null, unverified, or irrelevant;
   - the final page count.

Do not include the coverage report inside the CV itself.

## Final validation checklist

Before returning the CV, verify that:

- Every factual claim is supported by `master-cv.json`.
- The target title is appropriate for the supplied job description.
- Employer names, role titles, dates, metrics, and links are unchanged.
- The most important job requirements have visible supporting evidence.
- No unsupported requirement has been presented as candidate experience.
- Contact details come from the JSON and no placeholder remains.
- No dummy name, company, URL, date, or example content remains.
- There are no empty headings or empty list items.
- Page breaks do not split an entry awkwardly.
- The rendered PDF uses A4 size and contains selectable text.
- The result is one or two pages according to the page-count rule.

