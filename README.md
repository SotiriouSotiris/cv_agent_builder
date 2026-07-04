# CV Builder

An evidence-first repository for interviewing a candidate, building a reusable career inventory, and generating either a generic or job-specific LaTeX CV.

## Getting started

### 1. Clone the repository locally

Install Git, then clone this repository and enter its directory:

```sh
git clone https://github.com/SotiriouSotiris/cv_agent_builder.git
cd cv_agent_builder
```

Work from this local copy. You do not need to fork the repository, create another GitHub repository, or push your personal files anywhere.

### 2. Open it with an AI coding agent

Open the cloned directory in a tool that can read and edit repository files, such as:

- Codex
- Claude Code
- Visual Studio Code with an agentic extension such as Claude
- Another coding agent that follows repository instruction files

The agent should read `AGENTS.md` before working. `CLAUDE.md` directs Claude-based tools to those same instructions.

### 3. Create your career inventory

Copy the example inventory to the working filename:

```sh
cp example.career_inventory.md career_inventory.md
```

You can also duplicate `example.career_inventory.md` in your editor and rename the copy to `career_inventory.md`. Do not edit the example itself. Your working inventory is ignored by Git so that personal career details are not committed accidentally.

### 4. Ask the agent to interview you

Start the interview with a prompt such as:

```text
Use the CV interview skill to interview me and complete career_inventory.md.
```

The agent will ask about your employment, achievements, projects, education, skills, preferences, and anything that needs clarification. You can provide old CVs, professional profiles, portfolios, links, certificates, or other useful resources. These are temporary evidence: the agent extracts confirmed facts into `career_inventory.md` without saving copies of the source files.

Continue until you have reviewed the completed inventory and confirmed that it is accurate. CV generation begins only after this interview is complete.

### 5. Choose the CV you want

Once `career_inventory.md` is complete, ask the agent to create either a generic CV or a CV tailored to a specific job. The two workflows are described below.

Before generating the LaTeX and PDF files, the agent will ask you to choose one of four committed structures in `cv_templates/`:

- Classic Monochrome
- Modern Blue
- Technical Teal
- Leadership Burgundy

Each option includes a self-contained `.tex` source and compiled PDF preview. The agent may recommend the best match for the role, but you choose the final structure and colour style.

## How it works

1. If `career_inventory.md` does not exist, the agent copies `example.career_inventory.md` to `career_inventory.md`.
2. The agent uses `skills/cv-interview/` to interview the candidate and fill the inventory with verified career facts.
3. The candidate may provide old CVs, links, profiles, or other source material during the interview. The agent inspects them but does not create persistent copies.
4. Once the inventory is complete, the agent can generate either a generic CV or use `skills/generate-job-cv/` for a specific job application.
5. `cv-language.md` defines the writing and accuracy standard for both kinds of CV.
6. `skills/generate-job-cv/references/professional-cv-guidance.md` summarises trusted official CV guidance used by the agent.

Repository-wide agent behaviour is defined in `AGENTS.md`.

## Evidence-based CV guidance

Every generated CV follows the repository's accuracy and language rules together with [professional CV guidance](skills/generate-job-cv/references/professional-cv-guidance.md) synthesised from official resources published by:

- The University of Oxford Careers Service
- The UK National Careers Service
- MIT Career Advising and Professional Development
- Harvard's Mignone Center for Career Success

The agent reads this guidance before drafting. It covers tailoring, evidence-based achievements, clear language, recruiter scanning, ATS-readable structure, market differences, and final PDF verification. These practices are informed defaults rather than a guarantee of interviews or hiring; explicit employer instructions take priority.

## Building the career inventory

Ask an agent to use `$cv-interview`. The interview is a distinct first stage: its output is a complete, verified `career_inventory.md`, not a CV.

The agent will ask for any existing CVs, professional profiles, portfolios, links, or other useful resources. These are temporary inputs: only verified career facts belong in `career_inventory.md`; the agent must not save copies of supplied source files anywhere.

## Creating a generic CV

After the interview is complete, use a prompt such as:

```text
Create a generic CV from my completed career_inventory.md.
```

The agent creates the LaTeX source and compiled PDF in:

```text
generic_cv/
```

This directory is intentionally ignored by Git.

## Creating a job-specific CV

First, create an application directory under `job_applications/`. Give it a descriptive name and copy the committed job template into it, for example:

```sh
mkdir -p job_applications/example-company-example-role
cp job_applications/_template/job.md job_applications/example-company-example-role/job.md
```

Open the new `job.md`, complete its metadata, and paste the full job description into it. The resulting structure must be:

```text
job_applications/<job-application-name>/
└── job.md
```

Then ask the agent to tailor your CV, naming the application directory:

```text
Use $generate-job-cv to create a job-specific CV for job_applications/example-company-example-role.
```

The agent reads `career_inventory.md` and the supplied `job.md`, then creates `cv.tex` and `cv.pdf` in the same application directory. It does not create or name the application directory on the user's behalf.

Both `generic_cv/` and `job_applications/` are retained in Git using placeholder files. The reusable `job_applications/_template/job.md` is also committed, while actual application folders and generated CV files are ignored. This keeps personal CVs and application material local.

## Publishing safely

Keep your career information and generated applications local. Review `career_inventory.md` and generated files before changing ignore rules, publishing them, or pushing them to another repository. Remove contact details, confidential employer information, and personal facts that should not be disclosed.

## Repository policy

This public repository is provided as a read-only starting point for personal use. Clone it and work locally. Pull requests and external contributions are not accepted. The licence still permits use, modification, and redistribution under its terms.

## Licence

MIT.
