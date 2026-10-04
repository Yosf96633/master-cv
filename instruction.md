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

## Mandatory clarification gate

Do not generate, populate, render, or export the CV in the first response.
Before doing any CV production, analyze the job description and ask the user
for a short tailoring decision. Wait for the user's answer before continuing.

Ask only questions that materially affect the CV. Combine them into one concise
message covering these points:

1. Confirm the target job title if it is ambiguous.
2. Ask how many projects to include and whether the user wants specific
   projects. Recommend the most relevant projects by name.
3. Show the proposed skill groups or technologies and ask the user what to add,
   remove, or emphasize.
4. Show any important job requirements that are not supported by
   `master-cv.json` and ask whether the user can provide truthful missing
   information. Never fill the gap yourself.
5. Ask about any optional preference that is not already fixed by this file,
   such as one versus two pages or experience-versus-project emphasis.

Also provide a brief proposed content plan: selected experience entries,
recommended projects, included skill groups, excluded unrelated material, and
expected page count. The user may reply naturally, for example: "Use two
projects, remove React, emphasize Linux and networking, and use two pages."

This clarification step is mandatory even when the job description appears
complete. If the user has already supplied all five decisions in the same
message, summarize the proposed selection and ask for confirmation rather than
repeating answered questions.

Do not create the CV until the user confirms or revises the plan.

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

## Strict relevance gate

This is a tailored CV, not a compressed copy of the master CV. Inclusion is
opt-in: every skill, project, and bullet must earn its place through relevance
to the job description or an explicit user request.

Classify candidate material before writing:

- **Directly relevant:** explicitly requested by the job description or a
  close verified equivalent. Prioritize it.
- **Supporting:** provides credible evidence for a responsibility, domain, or
  transferable requirement. Include only when it strengthens the application
  and space permits.
- **Unrelated:** has no meaningful connection to the target role. Exclude it.

Rules:

- Do not dump the complete skills inventory into the CV.
- Do not include a technology merely because it exists in `master-cv.json`.
- A technology absent from the job description must be excluded unless the
  user explicitly requests it or it is essential evidence inside a selected,
  relevant accomplishment.
- Even when a technology appears inside a selected accomplishment, do not add
  it to the Skills section unless it is relevant to the target role.
- For a networking or infrastructure role, exclude unrelated frontend stacks
  such as React, Next.js, Tailwind CSS, Redux, and UI libraries unless the job
  description or user explicitly asks for them.
- For a frontend role, exclude unrelated AI, security, systems, or backend
  technologies unless they are requested or clearly support a selected duty.
- Apply the same filtering to projects. Select projects for relevance, not
  prestige, recency, stored rank, or technical complexity.
- Default to two or three highly relevant projects only after asking the user;
  follow the user's confirmed count.
- Experience entries may be retained for chronology, but their bullets must be
  filtered to relevant or strongly transferable evidence. Omit an entire role
  when it contributes no useful evidence and the user approves the proposed
  omission.
- Contact information, target title, and education are structural CV content
  and do not need to repeat job-description keywords.
- When no verified evidence supports a major requirement, list it in the
  coverage report as a gap. Do not compensate with unrelated material.

## Tailoring process

1. Extract the job title, responsibilities, required skills, preferred skills,
   domain terms, seniority, and repeated keywords from the job description.
2. Match those requirements against verified evidence in `master-cv.json`.
3. Classify every candidate skill, bullet, and project as directly relevant,
   supporting, or unrelated.
4. Prepare the proposed content plan and complete the mandatory clarification
   gate. Wait for confirmation.
5. Apply the user's confirmed project count, inclusions, exclusions, and
   emphasis.
6. Select the strongest directly relevant evidence first. Add supporting
   evidence only when it improves the application.
7. Prioritize demonstrated skills over standalone skill keywords.
8. Write a concise target-specific summary using only selected, supported
   facts. Do not mention unrelated areas of expertise.
9. Order skills and projects by job relevance rather than by the order in the
   JSON.
10. Preserve reverse-chronological order inside retained experience and
    education entries.
11. Remove unrelated content before reducing font size or spacing.
12. Populate the HTML template, render the PDF, inspect the rendered pages, and
    run the validation checklist below.

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

## PDF-first delivery rule

The required final CV artifact is a PDF. Do not return HTML as the primary or
final CV deliverable.

- Use `cv-template.html` as the fixed layout and styling blueprint.
- Populate a working copy of the HTML only as an intermediate rendering step.
- Render that populated template to an A4 PDF.
- Return or attach the finished `.pdf` file to the user.
- Do not stop after writing HTML, Markdown, JSON, LaTeX, or a code block.
- Do not ask the user to perform the PDF conversion when the current
  environment can create the PDF.
- If the environment genuinely cannot create or attach a PDF, state that
  limitation before generating any substitute. Never claim a PDF was created
  when it was not.
- The final PDF must visually follow `cv-template.html`: centered identity and
  contact block, single-column layout, matching typography hierarchy,
  horizontal section rules, right-aligned dates, black text, white background,
  and clean A4 page breaks.
- Inspect every rendered page rather than trusting the source HTML alone.
- The PDF must contain selectable text, working readable links, no clipping,
  no overlaps, no missing content, and no unintended blank page.

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

1. The completed PDF CV as the primary artifact.
2. A short coverage report listing:
   - job requirements supported by the CV;
   - important requirements not supported by the JSON;
   - the skills and projects deliberately excluded as unrelated;
   - any information omitted because it was null, unverified, or irrelevant;
   - the final page count.

Do not include the coverage report inside the CV itself. Keep the populated
HTML as an intermediate file unless the user explicitly asks to receive it.

## Final validation checklist

Before returning the CV, verify that:

- Every factual claim is supported by `master-cv.json`.
- The target title is appropriate for the supplied job description.
- Employer names, role titles, dates, metrics, and links are unchanged.
- The most important job requirements have visible supporting evidence.
- No unsupported requirement has been presented as candidate experience.
- Every included skill, bullet, and project passed the strict relevance gate or
  was explicitly requested by the user.
- Unrelated technology stacks are absent from both the Skills and Projects
  sections.
- The generated content matches the user's confirmed project count, skill
  scope, exclusions, and emphasis.
- Contact details come from the JSON and no placeholder remains.
- No dummy name, company, URL, date, or example content remains.
- There are no empty headings or empty list items.
- Page breaks do not split an entry awkwardly.
- The rendered PDF uses A4 size and contains selectable text.
- The result is one or two pages according to the page-count rule.
- The final delivered artifact is a real PDF, not only HTML or instructions for
  creating one.
