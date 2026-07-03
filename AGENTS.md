# CV Builder Agent Instructions

## Purpose

This repository interviews a candidate to build a verified career inventory, then produces reproducible generic or job-specific CVs from it. Treat accuracy as more important than persuasive wording. Never invent or silently strengthen a title, date, metric, responsibility, technology, qualification, or outcome.

## Source hierarchy

Use sources in this order:

1. The user's current, explicit instructions.
2. Confirmed facts in `career_inventory.md`.
3. The relevant application's `job.md` for the employer's language and requirements.
4. Public links, an existing CV, and other supplied material as supporting evidence.

If sources conflict, ask the user which fact is current. Do not resolve factual conflicts by guessing. Treat public marketing copy as product context, not proof that the candidate personally delivered a feature.

## Repository structure

```text
cv_builder/
├── AGENTS.md
├── README.md
├── LICENSE
├── career_inventory.md
├── cv-language.md
├── cv_templates/                  # Committed CV structures and PDF previews
│   ├── README.md
│   ├── classic-monochrome.{tex,pdf}
│   ├── modern-blue.{tex,pdf}
│   ├── technical-teal.{tex,pdf}
│   └── leadership-burgundy.{tex,pdf}
├── generic_cv/                     # Generated generic CV; ignored by Git
│   ├── *.tex
│   └── *.pdf
├── skills/
│   ├── cv-interview/
│   │   ├── SKILL.md
│   │   ├── agents/openai.yaml
│   │   └── references/question-bank.md
│   └── generate-job-cv/
│       ├── SKILL.md
│       └── agents/openai.yaml
└── job_applications/
    ├── _template/job.md
    └── <user-provided-application-name>/
        ├── job.md
        ├── cv.tex
        └── cv.pdf
```

The user creates and names each application directory and provides its `job.md`. Do not create, copy, rename, or choose a name for a job-application directory. Keep application-specific facts and the full job advertisement in `job.md`; job URLs can expire or change.

## Career-inventory workflow

1. If `career_inventory.md` is absent, copy `example.career_inventory.md` to `career_inventory.md` before starting the interview. Do not replace an existing inventory.
2. Read `skills/cv-interview/SKILL.md` completely and conduct the interview.
3. Ask the candidate for any old CVs, profiles, links, portfolios, certificates, publications, or other useful resources.
4. Inspect supplied material before asking questions it may already answer. Treat it as temporary input: do not copy, move, or save persistent copies of source files anywhere.
5. Record only confirmed facts and explicit uncertainty in `career_inventory.md`.
6. Continue until the inventory gives a comprehensive account of the candidate's CV-relevant history, evidence, skills, preferences, and cautions, with any remaining unknowns clearly marked.
7. Keep CV generation separate. Completing the interview does not automatically author a CV.

## Required reading

Before writing or revising any CV:

1. Read `career_inventory.md` completely.
2. Read `cv-language.md` completely.
3. For a job-specific CV, read the user-provided application's `job.md` completely.
4. Read `skills/cv-interview/SKILL.md` and resume the interview when facts are missing, ambiguous, outdated, or the user requests an interview.
5. Inspect any supplied CV or links before asking questions they may already answer, without storing persistent copies.
6. For a job-specific CV, read and follow `skills/generate-job-cv/SKILL.md` completely.
7. Read `cv_templates/README.md`, ask the user to choose a template, then read the selected `.tex` file completely before drafting.

## Career inventory rules

- Treat `career_inventory.md` as the canonical factual database, not text to copy wholesale.
- Preserve useful facts even when they do not fit the current CV.
- Add or change facts only after the user confirms them or provides an authoritative source.
- Record uncertainty explicitly with `Approximate`, `Planned`, `In progress`, or `Needs confirmation`.
- Keep official job titles distinct from leadership responsibilities. Never convert unofficial leadership into an official title.
- Keep private, confidential, or preference-sensitive information marked so it is not included automatically.
- Reconfirm time-sensitive facts such as current employment, planned launches, user counts, and contact details before important applications.

## Generic-CV workflow

1. Require a completed `career_inventory.md`; resume the interview if it is absent or materially incomplete.
2. Select evidence that gives the strongest accurate general account of the candidate without pretending to target a particular vacancy.
3. Present the committed CV template options, recommend a suitable option, and ask the user which structure and colour style they prefer.
4. Create or update the LaTeX source and PDF in `generic_cv/` using the selected template.
5. Apply the construction, compilation, visual-inspection, and ATS checks below.

## Job-specific CV workflow

1. Require the user to provide an existing directory under `job_applications/` containing `job.md`. If either is missing, ask the user to provide it; do not create the directory or populate the description for them.
2. Read `job.md` completely and confirm it contains the job description needed for tailoring.
3. Map each important requirement to verified evidence in `career_inventory.md`.
4. Identify genuine gaps. Do not hide them with unsupported claims.
5. Ask focused follow-up questions only where answers could materially improve the application, and add newly confirmed reusable facts to `career_inventory.md`.
6. Select the strongest relevant evidence. Tailoring means prioritising and wording facts, not changing them.
7. Create `cv.tex` inside the user-provided application directory. Do not edit files in `generic_cv/` as part of a tailored application.
8. Compile `cv.tex` to `cv.pdf` in the same directory.
9. Render the PDF to images and visually inspect every page. Correct clipping, overlap, awkward wrapping, excessive whitespace, tiny type, broken glyphs, and inconsistent spacing.
10. Extract text from the final PDF and verify that headings, dates, contact information, and keywords remain readable to an ATS.
11. Report the files created and any facts that still need confirmation.

## CV construction rules

- Do not draft or compile until the user chooses a committed template or explicitly requests a custom variation.
- Prefer one page. Use two pages only when the additional evidence is relevant and materially strengthens the application.
- Keep the layout single-column or otherwise reliably machine-readable.
- Use conventional headings such as `Profile`, `Experience`, `Education`, and `Technical Skills`.
- Keep contact links clickable and visible as human-readable labels.
- Use British English unless the job advertisement or user requests another variant.
- Use present tense for current responsibilities and past tense for completed or previous work.
- Prefer evidence-rich bullets that communicate action, technical scope, constraints, ownership, and result.
- Include metrics only when supplied or confirmed. Qualitative impact is acceptable when the candidate prefers not to disclose numbers.
- Include job-description terminology only when it truthfully describes the candidate's experience.
- Do not keyword-stuff, use progress bars, self-assessed skill percentages, decorative charts, photographs, or sensitive personal attributes unless explicitly requested and appropriate for the market.
- Never claim that planned, experimental, or in-progress functionality is already live.
- Do not claim ownership of work performed by colleagues. State collaboration and team boundaries accurately.

## LaTeX and PDF rules

- Keep the LaTeX source self-contained and reproducible.
- Use stable, commonly available packages.
- Escape LaTeX-sensitive characters in user and job-advertisement text.
- Prefer ASCII hyphens in source where typography does not require otherwise.
- Compile with an available engine such as Tectonic, `latexmk`, or `xelatex`.
- Do not commit `.aux`, `.log`, `.out`, `.xdv`, SyncTeX, or other intermediate files.
- The final PDF must have correct metadata, selectable text, working links, and no visual defects.

## Generic CV

`generic_cv/` is the local, ignored output directory for the current general-purpose CV and its LaTeX source. Tailored work belongs only in the user-provided directory under `job_applications/`. Git retains both parent directories through `.gitkeep` files and tracks `job_applications/_template/job.md`, while ignoring actual application contents.

## Safety and repository hygiene

- Do not include employer-confidential details, credentials, secrets, or private source code.
- Never ask the user to share account passwords. If a site requires authentication, ask for an export or pasted content.
- Preserve unrelated user changes.
- Do not commit, push, publish, or submit an application unless the user explicitly asks.
- Keep generic and job-specific CV files local. Git ignores `generic_cv/` contents and real application folders, but tracks `job_applications/_template/job.md`.
