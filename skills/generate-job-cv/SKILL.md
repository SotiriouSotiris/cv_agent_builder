---
name: generate-job-cv
description: Generate and verify a job-specific LaTeX CV and compiled PDF from a user-provided application directory containing job.md and the repository's career_inventory.md, including guided selection from committed CV templates. Use when the user asks to create, tailor, revise, compile, or regenerate cv.tex and cv.pdf for a specific vacancy.
---

# Generate Job CV

Create an accurate, evidence-based `cv.tex` and `cv.pdf` inside a user-provided job-application directory. Tailor by selecting and wording verified evidence, never by changing facts.

## 1. Locate and validate the application

Require the user to identify an existing directory under `job_applications/`.

Check for `job.md` inside that directory. If it is missing or does not contain the job description, stop and ask the user to provide or complete it. Do not create the application directory or reconstruct the advertisement from a URL unless the user explicitly asks.

Write all tailored outputs only inside the identified application directory.

## 2. Read the sources

Read these files completely before selecting CV content:

1. Repository-root `AGENTS.md`.
2. Repository-root `career_inventory.md`.
3. Repository-root `cv-language.md`.
4. `references/professional-cv-guidance.md` from this skill.
5. The application's `job.md`.

If `career_inventory.md` is missing or materially incomplete, use the repository's CV interview workflow before drafting. Inspect an existing application `cv.tex` or generic CV only as a layout reference; never treat it as a stronger factual source than the inventory.

Resolve factual conflicts with the user. Do not guess which source is current.

## 3. Analyse the vacancy and map evidence

Identify:

- The role's core responsibilities and outcomes.
- Required and preferred experience.
- Important technologies, domain knowledge, seniority, and collaboration expectations.
- Location, language, eligibility, and application constraints.
- Truthful job-description terminology that may help ATS matching.

Map each important requirement to specific evidence in `career_inventory.md`. Separate strong matches, partial matches, and genuine gaps. Do not hide gaps with vague wording, keyword stuffing, title inflation, or unsupported proficiency.

Prioritise evidence by relevance and strength. Preserve the candidate's official titles, dates, scope, ownership boundaries, and status of planned or in-progress work.

## 4. Ask focused follow-up questions

Ask the user only for information that could materially strengthen or correct this application. Group a small number of related questions and explain which job requirement prompted them.

Probe for missing scope, personal ownership, technical decisions, constraints, collaboration, and outcomes. Seek metrics without pressuring the user to disclose confidential figures. Accept a genuine gap when no supporting experience exists.

When the user confirms new reusable career information:

1. Update `career_inventory.md` immediately using its existing structure.
2. Record uncertainty with labels such as `Approximate`, `Planned`, `In progress`, or `Needs confirmation`.
3. Preserve unrelated confirmed facts.
4. Ask the user to resolve contradictions before using the new claim.

Do not store job-specific employer wording as a candidate fact unless the user confirms that it accurately describes their experience.

## 5. Ask the user to choose a template

Before writing `cv.tex`, read `cv_templates/README.md` and inspect the four committed templates and their compiled PDF previews. Present the user with these choices and a one-sentence trade-off for each:

1. **Classic Monochrome**: traditional structure for conservative employers and broad applications.
2. **Modern Blue**: clean contemporary structure that leads with selected impact.
3. **Technical Teal**: compact engineering structure that promotes skills and projects.
4. **Leadership Burgundy**: senior structure that foregrounds leadership scope and progression.

Recommend one option based on the vacancy, but ask the user which they prefer. Do not begin writing or compiling the CV until the user chooses a template or explicitly requests a custom variation. Do not infer a colour or structure preference from the job description alone.

Use the selected template as the structural and visual starting point. Do not combine templates unless the user asks. Preserve ATS readability when making requested adjustments.

## 6. Plan and write the LaTeX CV

Read and apply every instruction in `cv-language.md` and `references/professional-cv-guidance.md`. Select the smallest set of evidence that presents the strongest truthful fit for the vacancy.

Prefer one page. Use two pages only when the additional relevant evidence materially improves the application. Use a single-column, ATS-readable layout with conventional headings, selectable text, visible human-readable contact labels, and working links.

Copy the selected template's structure into `<application-directory>/cv.tex`, then replace every example placeholder with selected, verified candidate information. Remove unused placeholder sections and text. Keep the result self-contained and reproducible with stable, commonly available packages. Escape LaTeX-sensitive characters and set accurate PDF metadata.

Use British English unless the user or job advertisement clearly requires another variant. Use present tense for current responsibilities and past tense for completed or previous work. Include only confirmed metrics and technologies. Do not include sensitive personal attributes, decorative charts, photographs, progress bars, or self-assessed percentages unless explicitly requested and appropriate.

## 7. Compile and correct the PDF

Compile `cv.tex` to `<application-directory>/cv.pdf` with an available engine such as Tectonic, `latexmk`, or XeLaTeX. Resolve compilation errors and meaningful warnings. Keep intermediate build files out of the final deliverables.

If no LaTeX engine is available, preserve the completed `cv.tex`, explain the missing dependency, and ask before installing software or using an external service.

## 8. Verify the final result

Do not treat successful compilation as completion.

1. Render every PDF page to an image and inspect it visually.
2. Correct clipping, overlap, broken glyphs, awkward wrapping, excessive whitespace, tiny type, and inconsistent spacing.
3. Extract text from the PDF and verify headings, dates, contact details, links, and important job keywords remain readable in a sensible ATS order.
4. Confirm every claim against `career_inventory.md` or the user's newly confirmed answers.
5. Confirm official titles, tenses, ownership wording, metrics, technologies, and planned-work status.
6. Recompile and repeat the checks after corrections.

## Completion standard

Finish only when both `cv.tex` and `cv.pdf` exist in the application directory, the PDF passes visual and text-extraction checks, and no unsupported claim remains. Report the output files, the evidence prioritised, any genuine gaps, and any facts that still need confirmation. Do not commit, publish, or submit the application unless the user explicitly asks.
