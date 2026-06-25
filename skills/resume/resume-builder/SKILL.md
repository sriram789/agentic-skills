---
name: resume-builder
description: >
  ATS-optimized resume builder that creates polished, interview-winning resumes targeting Lead/Staff Engineer roles at big tech companies (Google, Meta, Amazon, Microsoft, Apple, Stripe, etc.). Use this skill whenever the user wants to build, rewrite, or improve a resume — especially for senior engineering roles. Trigger when the user mentions resume, CV, job application, ATS, interview calls, big tech, FAANG, Lead engineer, Staff engineer, or wants to present their career experience in a document format. Also trigger when the user shares background files (performance reviews, self-assessments, project write-ups) and wants a resume generated from them. Actively rewrites and strengthens bullet points for maximum ATS pass-through and recruiter impact — does not just format what's given.
---

# ATS-Optimized Resume Builder

Your goal is to produce a resume that does two things well: (1) pass ATS (Applicant Tracking System) filters at big tech companies, and (2) compel a human recruiter or hiring manager to pick up the phone. These goals are complementary — a keyword-rich, achievement-dense resume wins on both fronts.

## ATS-first principles (understand these before writing a single word)

ATS systems at Google, Meta, Amazon, and similar companies parse resumes before a human ever sees them. A resume that looks beautiful but fails ATS is invisible. The rules:

- **Single-column layout only** — multi-column, tables used for layout, and text boxes confuse parsers
- **Standard section names** — use exactly: Summary, Experience, Skills, Projects, Education, Certifications
- **No headers/footers for content** — ATS often ignores header/footer regions entirely
- **Standard fonts** — Arial or Calibri, 10–12pt body, never embed fonts as images
- **No graphics, icons, or images** — including profile photos, skill bars, rating dots
- **Keywords must appear in context** — "Java" in a bullet about what you built beats "Java" in a skills list
- **Bullet points, not paragraphs** — ATS scores keyword density; short bullets score higher than prose
- **Dates in consistent format** — "Jan 2023 – Present" or "2021 – 2023", never mixed

## Step 1: Read the input files

The user points you to a folder. Read every file in it — performance reviews, self-assessments, award nominations, project write-ups, previous resumes, anything. Extract:
- Job titles, companies, employment dates
- Responsibilities, achievements, projects
- Quantifiable results (numbers, percentages, scale, time savings)
- Technologies, tools, frameworks, methodologies
- Certifications, courses, awards

## Step 2: Gather targeting information

Ask these questions — they directly determine keyword strategy and positioning:

**Batch 1 (required):**
- What specific role are you targeting? (e.g., "Lead Software Engineer", "Staff Backend Engineer", "Principal Engineer")
- Which companies are highest priority? (This shapes keyword emphasis — Google loves "scalability" and "distributed systems"; Amazon loves "ownership" and "impact at scale"; Meta loves "growth" and "infrastructure")
- Do you have a job description you'd like to optimise against? If yes, paste it or share the file — this is the single highest-leverage input for ATS optimisation.
- What's your preferred output format — `.docx`, `.pdf`, or both?

**Batch 2 (fill gaps from files):**
- What's the most impressive project that might not be obvious from documents?
- Any open source contributions, public talks, or published writing?
- Preferred resume length — 1 page or 2 pages? (For 8+ years of experience targeting senior roles, 2 pages is standard and expected at big tech.)

## Step 3: Keyword strategy

Before writing, build a keyword list from two sources:

1. **From the job description** (if provided): extract every technical term, tool, methodology, and soft-skill phrase that appears. These become required keywords.
2. **From big tech job patterns for Lead/Staff roles**: regardless of JD, these clusters consistently appear in ATS filters:
   - *Backend*: distributed systems, microservices, system design, high availability, fault tolerance, scalability, low latency
   - *AI/ML*: LLM, AI agents, machine learning, model deployment, inference, embeddings, RAG, prompt engineering
   - *Infrastructure*: Kafka, Kubernetes, Docker, AWS/GCP/Azure, CI/CD, observability, Prometheus, Grafana
   - *Leadership*: technical leadership, cross-functional, mentorship, architecture, roadmap, stakeholder

Map these keywords to specific experiences in the user's background. Every keyword should appear in a bullet, not just in the Skills section.

## Step 4: Rewrite bullets for maximum impact

This is where most resumes fail. Transform every bullet using this formula:

**Formula:** `[Strong verb] + [what you built/did] + [scale/context] + [quantified result]`

Weak: "Worked on backend services for the AI team"
Strong: "Architected event-driven Kafka pipeline processing 2M+ daily AI agent interactions, reducing end-to-end latency by 40%"

Weak: "Improved debugging process"
Strong: "Built AI Thread Analyser tool reducing agent debugging time from 45 minutes to <5 minutes; adopted by 3+ teams, cutting L2 escalations by 60%"

**Strong verb bank for senior engineering roles:**
Architected · Designed · Led · Owned · Drove · Scaled · Optimised · Reduced · Eliminated · Launched · Delivered · Migrated · Automated · Standardised · Mentored · Enabled

**Rules for bullets:**
- Start with a past-tense strong verb (even for current role — ATS prefers consistency)
- Include at least one number per bullet (users, requests, %, time, $, team size)
- Keep to one line where possible; two lines maximum
- If you don't have exact numbers, use informed estimates with context: "~2M daily", "50% reduction", "10+ engineers"
- 4–6 bullets per role is the sweet spot for senior roles

## Step 5: Build the resume structure

Use this exact section order and naming:

```
[FULL NAME]
[City, Country] · [Email] · [Phone] · [LinkedIn URL] · [GitHub URL]

SUMMARY
[3–4 lines maximum]

EXPERIENCE
[Role Title] · [Company] · [Start – End]
• bullet
• bullet

SKILLS
[Grouped by category, comma-separated, no ratings or bars]

PROJECTS  (include if projects are notable and distinct from work experience)
[Project Name] · [Tech stack] · [Date/duration]
• bullet

EDUCATION
[Degree] · [Institution] · [Year]

CERTIFICATIONS  (if any)
```

### Summary section

The summary is the only prose section. It should be 3–4 lines that:
1. State the role you're targeting and your years of experience
2. Name 2–3 specific technical domains you're strongest in
3. Include one standout achievement with a number
4. End with what you're looking for

It functions as an executive summary for the recruiter *and* as a dense keyword block for ATS. Don't make it generic — make it specific enough that it could only describe this person.

### Skills section

Group skills into 3–4 categories. Keep it flat — no ratings, no bars, no icons:

```
Languages: Java, Python, JavaScript, TypeScript, SQL
Backend & Distributed Systems: Spring Boot, Apache Kafka, Elasticsearch, Redis, Microservices, System Design
AI / LLM: LLM Integration, AI Agents, Prompt Engineering, MCP (Model Context Protocol), RAG, Azure OpenAI
Cloud & DevOps: AWS, Docker, Kubernetes, ArgoCD, Prometheus, Grafana, CI/CD
```

## Step 6: Generate the document

### For .docx output
Use `docx` npm package. Install with `npm install docx` in the output directory if needed.

**Critical ATS formatting rules for docx:**
- Single section, no columns
- No tables used for layout (tables for data only, if needed at all)
- No text boxes
- No headers/footers
- Font: Arial or Calibri, 10.5pt body, 11pt for role titles, 13–14pt for name
- Margins: 0.75 inches all sides (gives space while staying ATS-safe)
- Bullet character: use `LevelFormat.BULLET` with `•` — never unicode manually
- Name: bold, 20–22pt, left-aligned
- Section headers: bold, 11pt, ALL CAPS, with a bottom border line for visual separation
- Line spacing: 1.0–1.15, with modest spacing between sections
- No color except black/dark gray (some ATS strip color; keep it safe)

### For .pdf output
Convert the .docx to PDF using LibreOffice:
```bash
python /path/to/scripts/office/soffice.py --headless --convert-to pdf resume.docx
```

### File naming
Name output files clearly:
- `[FirstName]_[LastName]_Resume_[TargetRole].docx`
- `[FirstName]_[LastName]_Resume_[TargetRole].pdf`

## Step 7: ATS self-check before delivering

Before handing the resume to the user, mentally verify:
- [ ] Every section uses the standard name (Experience, not "Work History")
- [ ] All dates are consistent format
- [ ] At least 8–10 of the target keywords appear in bullet context (not just Skills)
- [ ] No bullet starts with "I" or "We" or "Responsible for"
- [ ] Every role has at least one quantified achievement
- [ ] No graphics, tables-as-layout, or multi-column formatting
- [ ] Skills section is complete and grouped

## Tone guidance

Be assertive. The user wants maximum reach — don't hedge or soften. If a bullet is weak, rewrite it strong and explain why. If a section is missing something important for big tech, say so and add it. The resume should read like the work of someone who is clearly ready for Lead/Staff — decisive, ownership-oriented, impact-focused.
