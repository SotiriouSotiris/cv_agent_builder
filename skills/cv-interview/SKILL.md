---
name: cv-interview
description: Interview a candidate and build or update the repository's verified, reusable career_inventory.md before any CV is written. Use when career_inventory.md is missing or incomplete, a person wants to create a CV from scratch, update outdated career facts, extract and confirm facts from old CVs or professional links, or fill factual gaps before generic or job-specific CV generation.
---

# CV Interview

Conduct an evidence-first interview that feels conversational rather than like a form. The deliverable is a comprehensive `career_inventory.md`; CV writing is a separate task after the interview.

## Initialise the inventory

At the start of the interview:

1. Check whether `career_inventory.md` exists at the repository root.
2. If it does not exist, copy `example.career_inventory.md` to `career_inventory.md` without changing the example.
3. If it exists, preserve its confirmed facts and update it in place.
4. Never replace an existing inventory with the example.

## Principles

- Ask open questions before narrow prompts.
- Ask for and inspect supplied old CVs, portfolios, profiles, repositories, product pages, certificates, publications, and other useful resources before asking for information they already contain.
- Treat supplied files and resources as temporary evidence. Do not copy, move, or save persistent copies of source files anywhere; store only confirmed facts in `career_inventory.md`.
- Treat public content as context. Confirm the candidate's personal contribution separately.
- Ask in short rounds, usually three to seven related questions. Do not send the entire questionnaire at once.
- Follow interesting evidence. Ask about scope, constraints, decisions, ownership, collaborators, and results.
- Seek metrics, but accept qualitative impact and confidentiality boundaries.
- Never invent or silently upgrade a title, date, metric, technology, proficiency, responsibility, or outcome.
- Separate official titles from unofficial leadership responsibilities.
- Mark planned and experimental work accurately.
- Do not ask for passwords or unnecessary sensitive personal attributes.

Read [references/question-bank.md](references/question-bank.md) when choosing follow-up questions or when a candidate's answers remain thin.

## Stage 1: Gather existing material

Ask for any existing or old CV, LinkedIn export or URL, GitHub profile, portfolio, product pages, publications, certificates, and other relevant resources. Accept that some candidates have none. Do not require a target job description: the inventory must be reusable for both generic and future job-specific CVs.

When files or links are available:

1. Inspect them first.
2. Extract a preliminary chronology and fact list.
3. Identify contradictions, missing dates, vague claims, and likely high-value areas.
4. Tell the candidate which sources were accessible and which were blocked.
5. Ask for an export or pasted text when authentication prevents access. Never request login credentials.

## Stage 2: Establish preferences

Ask which kinds of work the candidate wants to pursue, where they may apply, and what they do or do not want emphasised. Capture broad positioning and preferences without narrowing the inventory to one vacancy.

Confirm basic contact details only when needed for the final artifact. Avoid collecting age, marital status, religion, identity numbers, or other sensitive attributes unless the candidate explicitly needs them for a lawful, market-specific reason.

## Stage 3: Build the chronology

Work through current employment, earlier roles, education, projects, publications, volunteering, awards, and relevant service. For each role, establish:

- Official organisation, title, location, and dates.
- Product or domain and intended users.
- Team structure and reporting or collaboration boundaries.
- Responsibilities actually performed.
- Technologies used professionally.
- Promotion or progression history.

Resolve overlapping dates and unofficial titles explicitly.

## Stage 4: Deepen the evidence

For the most relevant recent roles, ask follow-ups about:

- Difficult technical or operational problems.
- Architecture and decisions personally owned.
- Constraints such as accuracy, scale, regulation, time, or legacy systems.
- Features, integrations, migrations, incidents, or launches.
- Leadership, mentoring, planning, review, and stakeholder work.
- Outcomes, adoption, reliability, time saved, revenue, cost, quality, or delivery speed.

Ask what collaborators handled so the final wording does not overclaim. When the candidate cannot disclose numbers, capture credible qualitative impact.

## Stage 5: Confirm skills

Derive a preliminary skills list from the evidence, then ask the candidate to correct it. Separate:

- Skills used professionally and currently.
- Skills used only in education or side projects.
- Tools the candidate no longer wants to market.
- Spoken languages and confirmed proficiency levels.

Do not infer expertise merely because a technology appears in a repository or job description.

## Stage 6: Reconcile and summarise

Before completing the interview, provide a concise factual summary containing:

- Positioning and preferences.
- Role chronology.
- Strongest verified achievements.
- Confirmed technical skills.
- Important exclusions or confidentiality preferences.
- Facts that remain approximate, planned, contradictory, or unconfirmed.

Ask the candidate to correct material inaccuracies. Minor wording choices do not require another interview round.

## Stage 7: Complete the inventory

Write the confirmed results into `career_inventory.md` throughout the interview. Before declaring it complete:

1. Preserve useful facts even if they do not fit the immediate CV.
2. Record dated metrics as snapshots.
3. Mark time-sensitive facts for future reconfirmation.
4. Record explicit cautions against title inflation or ownership overstatement.
5. Keep confidential information out of public files.
6. Cover all relevant sections from the example inventory, marking genuine unknowns explicitly rather than silently omitting them.
7. Ask the candidate to verify the completed inventory and correct material inaccuracies.

Do not overwrite confirmed facts because a new source uses different marketing language. Surface the discrepancy.

## Completion standard

The interview is complete when `career_inventory.md` contains a comprehensive, candidate-verified account of CV-relevant history, personal work versus team output, achievements, skills, education, links, preferences, exclusions, and remaining uncertainties. At that point the agent should have enough verified context to build either a generic CV or, after the user provides an application directory with `job.md`, a job-specific CV. Do not generate a CV as part of this skill unless the user separately requests it.
