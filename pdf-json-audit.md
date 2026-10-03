# PDF and master JSON content audit

Compared on 2026-10-03:

- `Muhammad_Yousaf_Associate_Software_Engineer_CV.pdf`
- `Muhammad_Yousaf_Associate_AI_Engineer_CV.pdf`
- `master-cv.json`

## Result

The PDFs and JSON overlap substantially, but neither contains all of the other.
The PDFs are targeted CVs, while the JSON is a broader master record.

## Present in the PDFs but missing or incomplete in JSON

| PDF information | JSON status | Action before merging |
| --- | --- | --- |
| Phone: `+92 335 8485732` | Missing (`phone` is `null`) | Confirm it should be public, then add it. |
| Target titles: Associate Software Engineer and Associate AI Engineer | Not present as alternate headlines | Add if these are approved target titles. |
| FSc Pre-Engineering, Royal College of Science Narowal, 2019–2021 | Missing | Confirm institution spelling and dates, then add to education. |
| Code Expert marked on-site | Location is `null` | Confirm and add. |
| Postman and VS Code | Missing from skill groups | Add if they should be searchable CV keywords. |
| AI Chatbots and AI Workflows | Not stored as literal skill labels | Add only if desired; the project evidence already demonstrates them. |
| Vidly processed 1,000 YouTube comments in 90 seconds | Missing | Confirm the benchmark conditions before adding. |
| Vidly supported exactly three concurrent analyses | JSON mentions concurrency but not the number | Confirm and add the number. |
| DocsAI used GPT-4o-mini for its validation gate | Validation exists, model name is missing | Confirm the production implementation/version. |
| DocsAI used `pdfplumber` for position-aware chunking | Chunking is present, library name is missing | Confirm and add. |
| AutoHunt scraped multiple boards and specifically navigated RemoteOK | Generic discovery/automation exists, sources are missing | Confirm current supported boards before adding. |
| Mozzine reusable component libraries, pixel-perfect delivery, and design/backend collaboration | Only partially represented | Decide whether these are accurate and worth adding. |
| Code Expert email examples: order confirmations, vendor notifications, password resets | Resend is present, examples are missing | Add only if these workflows were implemented personally. |

## Inconsistency requiring confirmation

The JSON assigns the `20+ Figma designs` achievement to Mozzine Technologies.
Both PDFs assign `20+ Figma screens` to Code Expert. This should not be merged or
duplicated until the correct employer is confirmed.

The Software Engineer PDF also says `Full Stack Inter`; the AI Engineer PDF and
JSON say `Full Stack Intern`. The latter appears to be the intended title.

## Present in JSON but omitted from one or both PDFs

- Independent self-employment beginning May 2026.
- Hiba Logics PHP Laravel internship.
- Seven projects beyond the projects selected across the two PDFs.
- C, C++, Rust, Bash, PHP, systems programming, security tools, and several backend/data technologies.
- Broader professional interests, generation safeguards, and project metadata.
- Additional project details for myShell, Better Auth Starter, Nest E-Commerce API, Event Horizon, Algo Arena, CamBot, and the portfolio.

These omissions are normal for targeted CVs and do not imply the JSON is wrong.

